# Maintainers team setup guide

Follow these steps once as an **organisation owner** to activate `@gdgoc-apu/maintainers` for CODEOWNERS and review routing.

## Option A — GitHub website (recommended)

1. Open [github.com/orgs/gdgoc-apu/teams](https://github.com/orgs/gdgoc-apu/teams)
2. Click **New team**
3. Set:
   - **Team name:** `maintainers`
   - **Description:** `Core reviewers and community leads for GDGoC APU`
   - **Visibility:** Visible (recommended for open source)
4. Click **Create team**
5. Add members (update the list in [MAINTAINERS.md](../MAINTAINERS.md) with real GitHub usernames):
   - `your-github-username`
6. Go to **Organisation settings → Member privileges → Base permissions** and confirm members can create repositories if needed
7. For each project repository, optionally set:
   - **Settings → Collaborators and teams → Add team `maintainers`**
   - Role: **Maintain** or **Write** (Maintain is recommended for reviewers)

## Option B — GitHub CLI

Install [GitHub CLI](https://cli.github.com/) and authenticate as an org owner:

```powershell
gh auth login
gh api -X POST orgs/gdgoc-apu/teams -f name=maintainers -f description="Core reviewers and community leads for GDGoC APU" -f privacy=closed
gh api -X PUT orgs/gdgoc-apu/teams/maintainers/memberships/your-github-username -f role=maintainer
```

Replace `your-github-username` with each maintainer's GitHub handle.

## Verify it works

1. Open any org repository and create a test pull request
2. Confirm `@gdgoc-apu/maintainers` is requested for review (from CODEOWNERS)
3. Open **Organisation → People → Teams** and confirm `maintainers` appears

## Optional org settings

| Setting | Location | Recommendation |
| --- | --- | --- |
| Pinned repositories | Org profile page | Pin `.github` and top projects as they launch |
| Org description | Org settings → Profile | `Google Developer Groups on Campus at Asia Pacific University` |
| Location | Org settings → Profile | `Kuala Lumpur, Malaysia` |
| Website | Org settings → Profile | [GDG Community chapter page](https://gdg.community.dev/gdg-on-campus-asia-pacific-university-of-technology-innovation-kuala-lumpur-malaysia/) |
| Discussion | Repo or org settings | Enable for contribution questions |

## Update this list

When maintainers change, update [MAINTAINERS.md](../MAINTAINERS.md) and the profile README team section in the same pull request.
