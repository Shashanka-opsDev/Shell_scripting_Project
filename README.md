GitHub Repository Access Audit Script 🔐
📌 Overview

This project is a Bash shell script that integrates with the GitHub REST API to list users who currently have read (pull) access to a specific GitHub repository.

It helps teams audit repository access and quickly identify users who still have access even after leaving the team.

This is especially useful for:

Security audits

Access reviews

Offboarding verification

DevOps automation workflows

🚀 How It Works

The script uses GitHub API to fetch repository collaborators.

It filters users who have read (pull) permissions.

When executed, it displays a list of users who currently have access to the repository.

👉 This allows teams to ensure only authorized members have access to sensitive repositories.

🛠️ Prerequisites

Before running the script, ensure you have:

Linux / macOS

Bash shell

curl

jq (JSON parser)

GitHub Personal Access Token (PAT)

Install jq (if not installed)
sudo apt install jq     # Ubuntu/Debian
brew install jq         # macOS

🔑 GitHub Personal Access Token

Create a GitHub PAT with the following permissions:

repo (for private repositories)

read:org (if repo belongs to an organization)

👉 Generate token from:
GitHub → Settings → Developer settings → Personal access tokens

⚙️ Script Configuration

Set your GitHub credentials as environment variables:

export username="your_github_username"
export token="your_personal_access_token"

▶️ Usage
Make the script executable
chmod +x github_repo_access_audit.sh

Run the script
./github_repo_access_audit.sh <REPO_OWNER> <REPO_NAME>

Example
./github_repo_access_audit.sh octocat hello-world

📤 Output Example
Listing users with read access to octocat/hello-world...
Users with read access to octocat/hello-world:
user1
user2
user3


If no users have read access:

No users with read access found for octocat/hello-world.

🎯 Real-World Use Case

When a team member leaves the organization, sometimes their GitHub access is not removed.

This script helps detect leftover access instantly.

Can be integrated into:

CI/CD pipelines

Periodic security audits

DevOps governance checks

🔐 Security Best Practices

❌ Do NOT hardcode GitHub tokens inside the script

✅ Use environment variables

✅ Rotate tokens periodically

✅ Limit token permissions to minimum required

📌 Future Enhancements (Optional Ideas)

List write/admin access users

Support organization-wide audit

Export results to a file (CSV/JSON)

Slack or email notifications

CI/CD pipeline integration

👨‍💻 Author

Shashanka K U
DevOps Engineer | AWS | Docker | Kubernetes | GitHub Automation
