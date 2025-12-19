# GitHub Repository Management & Privacy Control

**Skill Name:** `github-repo-manager`  
**Version:** `1.0.0`  
**Last Updated:** December 18, 2024  
**Author:** Markus Dejmek  
**Category:** Development Tools / Version Control

## Overview
This skill provides comprehensive guidance for accessing and managing GitHub repositories using the GitHub API and CLI tools. It emphasizes privacy-first practices, ensuring all repositories are private by default. Covers authentication, repository operations, privacy controls, and common workflows.

## Authentication

### Using Stored Credentials
Load credentials from the configuration file:
```bash
source /Users/mdejmek/Documents/desktopc/github_config.txt
# This sets: github_token and github_username variables
```

### API Authentication Header
```bash
-H "Authorization: token ${github_token}"
-H "Accept: application/vnd.github.v3+json"
```

## 🔒 Privacy & Security Settings

### CRITICAL: Default Repository Privacy
**ALL new repositories MUST be created as PRIVATE by default.**

### Set GitHub Account Default to Private
1. Visit: https://github.com/settings/repositories
2. Under "Repository default visibility" select **Private**
3. This ensures web-created repositories are private by default

### Check for Public Repositories (ALERT FUNCTION)
Use this function to scan for any public repositories and get alerts:

```bash
gh_check_public() {
    source /Users/mdejmek/Documents/desktopc/github_config.txt
    echo "🔍 Scanning for public repositories..."
    
    public_repos=$(curl -s -H "Authorization: token ${github_token}" \
         -H "Accept: application/vnd.github.v3+json" \
         "https://api.github.com/user/repos?per_page=100&visibility=public" | \
         jq -r '.[] | .name')
    
    if [ -z "$public_repos" ]; then
        echo "✅ All repositories are private"
    else
        echo "⚠️  WARNING: Found PUBLIC repositories:"
        echo "$public_repos" | while read repo; do
            echo "  🔓 ${repo} - https://github.com/${github_username}/${repo}"
        done
        echo ""
        echo "To make them private, visit repository settings or use:"
        echo "  gh_make_private REPO_NAME"
    fi
}
```

### Convert Repository to Private
```bash
# Function to make a repository private
gh_make_private() {
    source /Users/mdejmek/Documents/desktopc/github_config.txt
    local repo_name=$1
    
    curl -X PATCH -H "Authorization: token ${github_token}" \
         -H "Accept: application/vnd.github.v3+json" \
         -d '{"private":true}' \
         "https://api.github.com/repos/${github_username}/${repo_name}"
    
    echo "✅ ${repo_name} is now private"
}
# Usage: gh_make_private vibe-mockup
```

## Common Operations

### 1. List Repositories
```bash
# List all repositories (public + private)
curl -H "Authorization: token ${github_token}" \
     -H "Accept: application/vnd.github.v3+json" \
     "https://api.github.com/user/repos?per_page=100&visibility=all"

# List only public repositories
curl -H "Authorization: token ${github_token}" \
     -H "Accept: application/vnd.github.v3+json" \
     "https://api.github.com/users/${github_username}/repos?per_page=100"

# List only private repositories
curl -H "Authorization: token ${github_token}" \
     -H "Accept: application/vnd.github.v3+json" \
     "https://api.github.com/user/repos?per_page=100&visibility=private"
```
### 2. Get Repository Details
```bash
# Get specific repository information
curl -H "Authorization: token ${github_token}" \
     -H "Accept: application/vnd.github.v3+json" \
     "https://api.github.com/repos/${github_username}/REPO_NAME"
```

### 3. List Repository Contents
```bash
# List files in repository root
curl -H "Authorization: token ${github_token}" \
     -H "Accept: application/vnd.github.v3+json" \
     "https://api.github.com/repos/${github_username}/REPO_NAME/contents"

# List files in specific directory
curl -H "Authorization: token ${github_token}" \
     -H "Accept: application/vnd.github.v3+json" \
     "https://api.github.com/repos/${github_username}/REPO_NAME/contents/path/to/dir"
```

### 4. Clone Repository
```bash
# Clone using HTTPS with token
git clone https://${github_token}@github.com/${github_username}/REPO_NAME.git

# Clone to specific directory
git clone https://${github_token}@github.com/${github_username}/REPO_NAME.git /path/to/destination
```

### 5. Read File Contents
```bash
# Get file content (returns base64 encoded)
curl -H "Authorization: token ${github_token}" \
     -H "Accept: application/vnd.github.v3+json" \
     "https://api.github.com/repos/${github_username}/REPO_NAME/contents/path/to/file.txt"
```
### 6. Create New Repository
**⚠️ IMPORTANT: Always create repositories as PRIVATE by default**

```bash
# Create PRIVATE repository (RECOMMENDED - DEFAULT)
curl -X POST -H "Authorization: token ${github_token}" \
     -H "Accept: application/vnd.github.v3+json" \
     -d '{"name":"new-repo","description":"Repository description","private":true}' \
     "https://api.github.com/user/repos"

# Create public repository (ONLY if explicitly required)
curl -X POST -H "Authorization: token ${github_token}" \
     -H "Accept: application/vnd.github.v3+json" \
     -d '{"name":"new-repo","description":"Repository description","private":false}' \
     "https://api.github.com/user/repos"
```

### 7. Get Repository Branches
```bash
curl -H "Authorization: token ${github_token}" \
     -H "Accept: application/vnd.github.v3+json" \
     "https://api.github.com/repos/${github_username}/REPO_NAME/branches"
```

### 8. Get Recent Commits
```bash
# Get last 10 commits
curl -H "Authorization: token ${github_token}" \
     -H "Accept: application/vnd.github.v3+json" \
     "https://api.github.com/repos/${github_username}/REPO_NAME/commits?per_page=10"
```

## Workflow Examples

### Example 1: Clone and Explore Repository
```bash
# Load credentials
source /Users/mdejmek/Documents/desktopc/github_config.txt

# Clone repository
cd /Users/mdejmek/Documents/desktopc
git clone https://${github_token}@github.com/${github_username}/vibe-mockup.git
```
# List files
cd vibe-mockup
ls -la

# View git status
git status
```

### Example 2: Create New Repository with Initial Content
```bash
# Load credentials
source /Users/mdejmek/Documents/desktopc/github_config.txt

# Create repository via API (PRIVATE by default)
curl -X POST -H "Authorization: token ${github_token}" \
     -H "Accept: application/vnd.github.v3+json" \
     -d '{"name":"my-new-project","description":"My project description","private":true}' \
     "https://api.github.com/user/repos"

# Initialize local repository and push
cd /Users/mdejmek/Documents/desktopc
mkdir my-new-project
cd my-new-project
git init
echo "# My New Project" > README.md
git add README.md
git commit -m "Initial commit"
git branch -M main
git remote add origin https://${github_token}@github.com/${github_username}/my-new-project.git
git push -u origin main
```

### Example 3: Get Repository Statistics
```bash
# Load credentials
source /Users/mdejmek/Documents/desktopc/github_config.txt

# Get repository details
curl -H "Authorization: token ${github_token}" \
     -H "Accept: application/vnd.github.v3+json" \
     "https://api.github.com/repos/${github_username}/vibe-mockup" | \
     jq '{name, size, language, stars: .stargazers_count, forks: .forks_count, created: .created_at}'
```
### Example 4: Search Repositories
```bash
# Search your repositories by keyword
curl -H "Authorization: token ${github_token}" \
     -H "Accept: application/vnd.github.v3+json" \
     "https://api.github.com/search/repositories?q=user:${github_username}+mockup"

# Search code across repositories
curl -H "Authorization: token ${github_token}" \
     -H "Accept: application/vnd.github.v3+json" \
     "https://api.github.com/search/code?q=user:${github_username}+extension:html"
```

## Advanced Operations

### Working with Issues
```bash
# List issues
curl -H "Authorization: token ${github_token}" \
     -H "Accept: application/vnd.github.v3+json" \
     "https://api.github.com/repos/${github_username}/REPO_NAME/issues"

# Create issue
curl -X POST -H "Authorization: token ${github_token}" \
     -H "Accept: application/vnd.github.v3+json" \
     -d '{"title":"Issue title","body":"Issue description"}' \
     "https://api.github.com/repos/${github_username}/REPO_NAME/issues"
```

### Working with Pull Requests
```bash
# List pull requests
curl -H "Authorization: token ${github_token}" \
     -H "Accept: application/vnd.github.v3+json" \
     "https://api.github.com/repos/${github_username}/REPO_NAME/pulls"
```

### Repository Settings
```bash
# Update repository settings
curl -X PATCH -H "Authorization: token ${github_token}" \
     -H "Accept: application/vnd.github.v3+json" \
     -d '{"description":"Updated description","has_wiki":false}' \
     "https://api.github.com/repos/${github_username}/REPO_NAME"
```
## Best Practices

### 1. Repository Privacy (CRITICAL)
- **ALWAYS create repositories as PRIVATE by default** (`"private":true`)
- Set GitHub account default to private: https://github.com/settings/repositories
- Run `gh_check_public` regularly to audit repository visibility
- Only make repositories public if explicitly required for open source
- Review and convert any accidental public repositories immediately

### 2. Token Management
- Store tokens in the configuration file at `/Users/mdejmek/Documents/desktopc/github_config.txt`
- Load credentials using `source` command before operations
- Use environment variables for automation scripts

### 3. Rate Limiting
- GitHub API allows 5,000 requests per hour for authenticated requests
- Check rate limit status:
```bash
curl -H "Authorization: token ${github_token}" \
     "https://api.github.com/rate_limit"
```

### 4. Pagination
- API returns 30 items by default, max 100 per page
- Use `per_page` parameter to control results
- Follow `Link` headers for pagination

### 5. Repository Organization
- Use clear, descriptive repository names
- Maintain README.md files in all repositories
- Use .gitignore to exclude sensitive files
- Tag releases for version control

## Quick Reference

### Essential URLs
- User repositories: `https://api.github.com/user/repos`
- Specific repo: `https://api.github.com/repos/${github_username}/REPO_NAME`
- Repo contents: `https://api.github.com/repos/${github_username}/REPO_NAME/contents`
- Search: `https://api.github.com/search/repositories?q=...`

### Common Status Codes
- 200: Success
- 201: Created
- 204: No Content (success, no response body)
- 401: Unauthorized (check token)
- 404: Not Found
- 422: Validation Failed

## Troubleshooting

### Issue: 401 Unauthorized
- Verify token is loaded: `echo $github_token`
- Check token permissions at https://github.com/settings/tokens
- Ensure token hasn't expired
### Issue: Clone Failed
- Check repository exists and you have access
- Verify token has repo scope permissions
- Ensure repository name is spelled correctly

### Issue: Rate Limit Exceeded
- Wait until rate limit resets (check with `/rate_limit` endpoint)
- Optimize queries to reduce API calls
- Cache results when possible

## Helper Functions

### Load GitHub Configuration
```bash
load_github() {
    source /Users/mdejmek/Documents/desktopc/github_config.txt
    echo "✓ GitHub credentials loaded"
    echo "  Username: ${github_username}"
}
```

### Quick Repository Clone
```bash
gh_clone() {
    source /Users/mdejmek/Documents/desktopc/github_config.txt
    local repo_name=$1
    cd /Users/mdejmek/Documents/desktopc
    git clone https://${github_token}@github.com/${github_username}/${repo_name}.git
    echo "✓ Cloned ${repo_name}"
}
# Usage: gh_clone vibe-mockup
```

### List All Repositories
```bash
gh_list_repos() {
    source /Users/mdejmek/Documents/desktopc/github_config.txt
    curl -s -H "Authorization: token ${github_token}" \
         -H "Accept: application/vnd.github.v3+json" \
         "https://api.github.com/user/repos?per_page=100&visibility=all" | \
         jq -r '.[] | "\(.name) [\(.visibility)] - \(.description // "No description")"'
}
```

## Resources

- GitHub API Documentation: https://docs.github.com/en/rest
- GitHub CLI: https://cli.github.com/
- Personal Access Tokens: https://github.com/settings/tokens