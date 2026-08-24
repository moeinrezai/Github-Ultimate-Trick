<div dir="rtl">

# راهنمای جامع GitHub — ترفندها، ابزارها و Workflow حرفه‌ای

</div>

---

## 1. ترفندهای URL و Web

<div dir="rtl">

### GitHub.dev

با فشردن کلید `.` در یک Repository، می‌توان آن را در ویرایشگر تحت مرورگر مشابه VS Code باز کرد.

</div>

```text
https://github.dev/USER/REPO
```

<div dir="rtl">

### Gitingest

یک Repository را به محتوای متنی ساختاریافته تبدیل می‌کند تا بتوان از آن برای دادن context به ابزارهای هوش مصنوعی استفاده کرد.

</div>

```text
https://gitingest.com/USER/REPO
```

<div dir="rtl">

### GitHub MCP Server

برای اتصال Agentهای هوش مصنوعی سازگار به Repositoryها، Issueها، Pull Requestها و سایر منابع GitHub استفاده می‌شود.

</div>

```text
https://github.com/github/github-mcp-server
```

<div dir="rtl">

### مشاهده فایل Raw

برای مشاهده محتوای خام یک فایل، از گزینه `Raw` استفاده کنید.

</div>

```text
File → Raw
```

<div dir="rtl">

### Permalink

برای ارجاع دادن به نسخه مشخصی از یک فایل، از Permalink استفاده کنید. این کار برای Review، مستندسازی و ارجاع دقیق به کد بسیار مفید است.

با فشردن کلید زیر نیز می‌توان URL مربوط به نسخه مشخص فعلی را ایجاد کرد:

</div>

```text
Y
```

<div dir="rtl">

### Compare

برای مقایسه Branch، Tag یا Commit با یکدیگر:

</div>

```text
https://github.com/USER/REPO/compare
```

---

## 2. میانبرهای مهم GitHub

<div dir="rtl">

| میانبر | کاربرد |
|---|---|
| `.` | باز کردن Repository در GitHub.dev |
| `T` | جستجوی سریع فایل‌ها |
| `L` | رفتن مستقیم به یک شماره خط |
| `B` | مشاهده Git Blame |
| `W` | جابه‌جایی سریع بین Branch یا Tag |
| `/` | فعال کردن Search |
| `?` | نمایش Keyboard Shortcuts |

### Git Blame

با `B` می‌توان بررسی کرد هر خط از فایل توسط کدام Commit و Contributor تغییر داده شده است.

</div>

---

## 3. جستجوی حرفه‌ای در GitHub

<div dir="rtl">

GitHub از Search Qualifierها برای محدود کردن نتایج جستجو پشتیبانی می‌کند.

### جستجو در یک Repository مشخص

</div>

```text
repo:facebook/react useState
```

<div dir="rtl">

### فیلتر بر اساس زبان

</div>

```text
language:javascript fetch
```

<div dir="rtl">

### جستجوی فایل با نام مشخص

</div>

```text
filename:package.json
```

<div dir="rtl">

### جستجو در یک مسیر مشخص

</div>

```text
path:src/components
```

<div dir="rtl">

### جستجوی عبارت دقیق

</div>

```text
"authentication failed"
```

<div dir="rtl">

### جستجوی Issue و Pull Request

برای Issue و PR نیز می‌توان از Filterها استفاده کرد. نمونه‌های کاربردی:

</div>

```text
is:issue state:open
is:pr state:open
assignee:USERNAME
author:USERNAME
label:"bug"
no:assignee
linked:pr
```

<div dir="rtl">

برای پروژه‌های تیمی، استفاده از Filterها باعث می‌شود Issueهای بدون مسئول، Bugها، PRهای باز و کارهای عقب‌افتاده سریع‌تر پیدا شوند.

</div>

---

## 4. Repository

<div dir="rtl">

### Fork

یک کپی از Repository شخص دیگر در حساب خود ایجاد می‌کند و معمولاً برای مشارکت در پروژه‌هایی که دسترسی مستقیم به آن‌ها ندارید استفاده می‌شود.

مسیر:

</div>

```text
Repository → Fork
```

<div dir="rtl">

### Star

برای ذخیره یک Repository در فهرست موردعلاقه و دسترسی آسان‌تر در آینده استفاده می‌شود.

</div>

```text
Repository → Star
```

<div dir="rtl">

### Watch

برای مدیریت Notificationهای مربوط به فعالیت‌های یک Repository استفاده می‌شود.

</div>

```text
Repository → Watch
```

<div dir="rtl">

### Topics

برای دسته‌بندی Repository و بهتر پیدا شدن آن در GitHub استفاده می‌شود.

</div>

```text
Repository → About → Topics
```

<div dir="rtl">

### Releases و Tags

برای مشخص کردن نسخه‌های منتشرشده پروژه استفاده می‌شوند.

</div>

```text
https://github.com/USER/REPO/releases
```

<div dir="rtl">

### README.md

README باید حداقل اطلاعاتی مانند موارد زیر را توضیح دهد:

- هدف پروژه
- قابلیت‌ها
- تکنولوژی‌ها
- روش نصب و راه‌اندازی
- Environment Variables
- نحوه اجرای پروژه
- نحوه اجرای Testها
- نحوه مشارکت
- Branching و Pull Request Workflow
- License

</div>

---

## 5. Branch و Git Workflow

<div dir="rtl">

برای توسعه یک Feature بهتر است مستقیماً روی `main` کار نشود.

</div>

```bash
git switch main
git pull origin main
git switch -c feature/initialize-django-project
```

<div dir="rtl">

### نام‌گذاری Branch

پیشنهاد:

</div>

```text
feature/<name>
fix/<name>
bugfix/<name>
refactor/<name>
docs/<name>
test/<name>
chore/<name>
```

<div dir="rtl">

برای پروژه‌های تیمی، نام Branch بهتر است با Issue مرتبط باشد.

مثلاً برای Issue شماره `#1`:

</div>

```text
feature/initialize-django-project-1
```

---

## 6. Commit حرفه‌ای

<div dir="rtl">

Commit باید کوچک، مشخص و قابل فهم باشد.

پیشنهاد برای Conventional Commits:

</div>

```text
feat: initialize django project
fix: handle invalid otp
docs: add project setup guide
test: add authentication tests
refactor: simplify user service
chore: update dependencies
ci: add github actions workflow
```

<div dir="rtl">

### اتصال Commit به Issue

در صورت استفاده صحیح از Reference یا Closing Keyword می‌توان Commit/PR را به Issue مرتبط کرد.

نمونه:

</div>

```text
Fixes #1
Closes #1
Resolves #1
```

<div dir="rtl">

> برای بستن خودکار Issue بهتر است Closing Keyword در متن Pull Request استفاده شود تا ارتباط تغییر با Issue واضح و قابل Review باشد.

</div>

---

## 7. Pull Request

<div dir="rtl">

Pull Request محل اصلی Code Review و ورود تغییرات به Branch اصلی است.

### Draft Pull Request

قبل از کامل شدن Feature می‌توان یک Draft PR ساخت تا اعضای تیم زودتر بازخورد بدهند.

مسیر:

</div>

```text
Pull Request → Create draft PR
```

<div dir="rtl">

### Files changed

برای مشاهده تمام تغییرات ایجادشده در PR:

</div>

```text
Pull Request → Files changed
```

<div dir="rtl">

### Suggested Changes

Reviewer می‌تواند تغییر پیشنهادی خود را مستقیماً روی کد پیشنهاد دهد.

مسیر:

</div>

```text
Pull Request → Review
```

<div dir="rtl">

### Checks

قبل از Merge باید وضعیت Testها، Lint و سایر CI Checkها بررسی شود.

</div>

```text
Pull Request → Checks
```

<div dir="rtl">

### Squash and Merge

چند Commit مربوط به یک Feature را هنگام Merge به یک Commit تمیز تبدیل می‌کند.

</div>

```text
Pull Request → Squash and merge
```

<div dir="rtl">

### پیشنهاد Workflow برای تیم

</div>

```text
Issue
  ↓
Create Branch
  ↓
Implement
  ↓
Commit
  ↓
Push
  ↓
Pull Request
  ↓
CI Checks
  ↓
Code Review
  ↓
Fix Review Comments
  ↓
Approve
  ↓
Squash and Merge
  ↓
Close Issue
```

---

## 8. Issue

<div dir="rtl">

Issue فقط برای Bug نیست. می‌توان از آن برای Feature، Task، Documentation، Refactor و سایر کارها استفاده کرد.

یک Issue خوب بهتر است شامل این موارد باشد:

- عنوان مشخص
- توضیح مسئله
- هدف
- Scope
- Acceptance Criteria
- مسئول
- Label
- Milestone
- وابستگی‌ها
- لینک به PR در صورت وجود

### نمونه عنوان

</div>

```text
Initialize Django Project #1
```

<div dir="rtl">

### Acceptance Criteria

</div>

```text
- Django project is created
- Required apps are initialized
- Environment configuration is added
- Project starts successfully
- README is updated
```

---

## 9. Labels

<div dir="rtl">

برای مدیریت بهتر Issueها و PRها از Label استفاده کنید.

نمونه:

</div>

```text
bug
feature
documentation
enhancement
refactor
testing
backend
frontend
priority:high
priority:medium
priority:low
good first issue
help wanted
```

<div dir="rtl">

بهتر است Labelها از ابتدا استاندارد شوند و اعضای تیم هر بار Label جدید و مشابه ایجاد نکنند.

</div>

---

## 10. Milestones

<div dir="rtl">

Milestone برای گروه‌بندی چند Issue در یک هدف یا نسخه مشخص استفاده می‌شود.

مثلاً:

</div>

```text
Milestone: v0.1 - Project Initialization
Milestone: v0.2 - Authentication
Milestone: v0.3 - Library Management
Milestone: v1.0 - Production Release
```

<div dir="rtl">

در یک پروژه آموزشی، Milestone می‌تواند نماینده یک مرحله از پروژه باشد.

</div>

---

## 11. GitHub Projects

<div dir="rtl">

GitHub Projects برای مدیریت Work در سطح تیم استفاده می‌شود.

می‌توان وضعیت‌هایی مانند موارد زیر ایجاد کرد:

</div>

```text
Backlog
Todo
In Progress
In Review
Blocked
Done
```

<div dir="rtl">

همچنین می‌توان Viewهای مختلف مانند Board و Table ساخت و Issueها و PRها را به Project متصل کرد.

</div>

---

## 12. Repository Permissions و نقش‌ها

<div dir="rtl">

در پروژه‌های تیمی باید Permissionها بر اساس اصل Least Privilege تنظیم شوند.

نقش‌های رایج Repository:

</div>

```text
Read
Triage
Write
Maintain
Admin
```

<div dir="rtl">

برای اعضای معمولی تیم، معمولاً نباید دسترسی `Admin` داده شود. مسئول پروژه می‌تواند Repository و Rules را مدیریت کند و اعضای توسعه‌دهنده با دسترسی مناسب کار کنند.

</div>

---

## 13. Branch Rules و Rulesets

<div dir="rtl">

برای جلوگیری از Push مستقیم و Merge ناخواسته به Branchهای حساس مانند `main`، از Repository Rules / Rulesets استفاده کنید.

قوانین مفید:

- Require a Pull Request
- Require approvals
- Require status checks
- Block force pushes
- Require code scanning results
- Restrict branch creation
- Restrict branch deletion

برای یک پروژه تیمی، یک سیاست مناسب می‌تواند این باشد:

</div>

```text
main
 ├── Direct Push: Disabled
 ├── Pull Request: Required
 ├── Approval: Required
 ├── CI Checks: Required
 └── Force Push: Disabled
```

---

## 14. GitHub Actions

<div dir="rtl">

GitHub Actions برای خودکارسازی Test، Build، Lint، Security Check و Deployment استفاده می‌شود.

فایل Workflow معمولاً در این مسیر قرار می‌گیرد:

</div>

```text
.github/workflows/
```

<div dir="rtl">

نمونه Workflow ساده برای پروژه Python:

</div>

```yaml
name: Django CI

on:
  push:
    branches:
      - main
  pull_request:

jobs:
  test:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout
        uses: actions/checkout@v4

      - name: Setup Python
        uses: actions/setup-python@v5
        with:
          python-version: "3.12"

      - name: Install dependencies
        run: pip install -r requirements.txt

      - name: Run tests
        run: python manage.py test
```

<div dir="rtl">

برای پروژه واقعی می‌توان مراحل بیشتری مانند `lint`، `format check`، `security scan`، Docker Build و Deployment اضافه کرد.

</div>

---

## 15. GitHub Secrets

<div dir="rtl">

مقادیر حساس مانند API Key، Password، Token و Credentials نباید در Repository Commit شوند.

Secrets مربوط به GitHub Actions را می‌توان از مسیر زیر مدیریت کرد:

</div>

```text
Settings → Secrets and variables → Actions
```

<div dir="rtl">

در Workflow:

</div>

```yaml
env:
  API_KEY: ${{ secrets.API_KEY }}
```

<div dir="rtl">

**هرگز Secret واقعی را در فایل‌هایی مانند موارد زیر Commit نکنید:**

</div>

```text
.env
.env.production
settings.py
config.json
docker-compose.override.yml
```

<div dir="rtl">

از `.gitignore` برای جلوگیری از Commit شدن فایل‌های حساس استفاده کنید.

</div>

```gitignore
.env
.env.*
!.env.example
__pycache__/
*.pyc
node_modules/
.venv/
```

---

## 16. GitHub Pages

<div dir="rtl">

برای میزبانی سایت‌های Static می‌توان از GitHub Pages استفاده کرد.

نمونه آدرس:

</div>

```text
https://USER.github.io/REPO/
```

<div dir="rtl">

برای Documentation پروژه‌ها نیز گزینه مناسبی است.

</div>

---

## 17. Security

<div dir="rtl">

GitHub امکانات امنیتی مهمی برای Repository ارائه می‌دهد.

### Dependabot

برای شناسایی Dependencyهای آسیب‌پذیر و ایجاد Pull Request برای به‌روزرسانی آن‌ها استفاده می‌شود.

### Secret Scanning

برای پیدا کردن Secretهای Commit شده در Repository استفاده می‌شود.

### Push Protection

در صورت فعال بودن، می‌تواند قبل از ورود برخی Secretهای شناسایی‌شده به Repository، Push را متوقف کند.

### Code Scanning

برای شناسایی آسیب‌پذیری‌ها و خطاهای کدنویسی استفاده می‌شود.

### Dependency Review

تغییرات Dependencyها را هنگام Pull Request بررسی می‌کند.

</div>

```text
Security / Code security
├── Dependabot
├── Secret scanning
├── Push protection
├── Code scanning
└── Dependency review
```

<div dir="rtl">

فعال‌سازی دقیق این قابلیت‌ها به نوع Repository و Plan حساب GitHub بستگی دارد.

</div>

---

## 18. Dependabot

<div dir="rtl">

برای پروژه‌های Python می‌توان Dependabot را برای بررسی Dependencyها فعال کرد.

نمونه:

</div>

```yaml
version: 2

updates:
  - package-ecosystem: "pip"
    directory: "/"
    schedule:
      interval: "weekly"

  - package-ecosystem: "github-actions"
    directory: "/"
    schedule:
      interval: "weekly"
```

<div dir="rtl">

این قابلیت به‌خصوص برای پروژه‌های Django، FastAPI و سایر پروژه‌های Python مفید است.

</div>

---

## 19. CODEOWNERS

<div dir="rtl">

فایل `CODEOWNERS` مشخص می‌کند چه افرادی یا تیم‌هایی Owner قسمت‌های مختلف Repository هستند و باید در Review تغییرات مربوط به آن قسمت‌ها مشارکت کنند.

مسیرهای رایج:

</div>

```text
.github/CODEOWNERS
CODEOWNERS
docs/CODEOWNERS
```

<div dir="rtl">

نمونه:

</div>

```text
# Backend
/backend/ @backend-team

# Documentation
/docs/ @maintainers

# GitHub Actions
/.github/workflows/ @devops-team
```

---

## 20. Discussions

<div dir="rtl">

GitHub Discussions برای گفت‌وگوهای عمومی‌تر پروژه مناسب است؛ مثلاً:

- سؤال و جواب
- ایده‌های جدید
- پیشنهاد Feature
- Announcement
- بحث معماری
- تجربه‌های تیم

برای یک Bug مشخص، Issue معمولاً انتخاب مناسب‌تری است.

</div>

---

## 21. GitHub Releases

<div dir="rtl">

Release برای انتشار نسخه‌های رسمی پروژه استفاده می‌شود.

یک Release معمولاً شامل:

- Version
- Tag
- Release Notes
- تغییرات مهم
- Bug Fixes
- Breaking Changes
- Assets

است.

نمونه Versioning:

</div>

```text
v1.0.0
v1.1.0
v1.1.1
```

<div dir="rtl">

برای پروژه‌هایی که نسخه‌بندی دارند، استفاده از Semantic Versioning بسیار مفید است.

</div>

---

## 22. GitHub Packages

<div dir="rtl">

GitHub Packages برای انتشار و نگهداری Packageها و Artifactهای پروژه استفاده می‌شود.

برای پروژه‌های Python می‌توان Packageهای داخلی را در Registry مناسب نگهداری کرد.

</div>

---

## 23. GitHub Codespaces

<div dir="rtl">

Codespaces یک محیط توسعه ابری برای کار روی Repository است و می‌تواند برای ایجاد محیط توسعه استاندارد تیمی استفاده شود.

برای پروژه‌های تیمی بزرگ‌تر، تعریف `devcontainer.json` می‌تواند باعث شود محیط توسعه اعضای تیم تا حد زیادی یکسان باشد.

</div>

---

## 24. GitHub Copilot و GitHub Models

<div dir="rtl">

PDF ارائه‌شده ابزارهای هوش مصنوعی GitHub مانند Copilot و GitHub Models را معرفی می‌کند.

### Copilot

برای پیشنهاد کد، توضیح کد و کمک در فرآیند توسعه استفاده می‌شود.

### GitHub Models

برای بررسی و آزمایش مدل‌های هوش مصنوعی موجود در اکوسیستم GitHub استفاده می‌شود.

### نکته مهم

ابزارهای AI باید به عنوان ابزار کمکی استفاده شوند، نه جایگزین Code Review، Test و درک معماری پروژه.

</div>

---

## 25. Gitingest و انتقال Context به AI

<div dir="rtl">

اگر هدف این است که یک AI ساختار پروژه را بهتر درک کند، انتقال Context مناسب اهمیت زیادی دارد.

یک Workflow ساده:

</div>

```text
GitHub Repository
       ↓
Gitingest / MCP
       ↓
Project Context
       ↓
AI Assistant
       ↓
Analysis / Coding / Documentation
```

<div dir="rtl">

برای پروژه‌های حساس، قبل از ارسال Repository به هر ابزار خارجی باید Secretها، اطلاعات خصوصی و داده‌های حساس بررسی شوند.

</div>

---

## 26. GitHub CLI

<div dir="rtl">

علاوه بر رابط وب، می‌توان بسیاری از عملیات GitHub را با GitHub CLI انجام داد.

</div>

```bash
gh auth login

gh repo clone OWNER/REPO

gh issue list

gh issue create

gh pr list

gh pr create

gh pr checkout 123

gh pr merge 123
```

<div dir="rtl">

این ابزار برای توسعه‌دهندگانی که با Terminal راحت هستند بسیار کاربردی است.

</div>

---

## 27. ارتباط Issue و Pull Request

<div dir="rtl">

یک Workflow حرفه‌ای باید ارتباط بین Task، Branch، Commit و PR را قابل ردیابی کند.

مثلاً:

</div>

```text
Issue #1
   ↓
feature/initialize-django-project-1
   ↓
Commit
   ↓
Pull Request #5
   ↓
Review
   ↓
Merge
   ↓
Issue #1 → Closed
```

<div dir="rtl">

این ساختار برای مدیریت پروژه تیمی بسیار مهم است، زیرا مشخص می‌کند هر تغییر کد برای چه کاری ایجاد شده است.

</div>

---

## 28. Workflow پیشنهادی برای پروژه تیمی

<div dir="rtl">

برای پروژه‌های Django، DRF، FastAPI و پروژه‌های مشابه، Workflow زیر پیشنهاد می‌شود:

</div>

```text
Manager creates Issue
        ↓
Assign Issue
        ↓
Developer creates Branch
        ↓
Developer implements Task
        ↓
Developer runs local tests
        ↓
Commit
        ↓
Push
        ↓
Open Pull Request
        ↓
GitHub Actions
        ↓
Code Review
        ↓
Changes Requested?
   ┌────┴────┐
  Yes        No
   ↓          ↓
Fix       Approve
   ↓          ↓
Push       Merge
   └────┬─────┘
        ↓
Close Issue
```

---

## 29. استاندارد پیشنهادی برای Repository آموزشی

<div dir="rtl">

برای یک پروژه آموزشی تیمی می‌توان Repository را به شکل زیر سازمان‌دهی کرد:

</div>

```text
repository/
├── .github/
│   ├── workflows/
│   ├── ISSUE_TEMPLATE/
│   ├── PULL_REQUEST_TEMPLATE.md
│   └── CODEOWNERS
│
├── docs/
│   ├── project-description.md
│   ├── git-workflow.md
│   ├── github-guide.md
│   └── architecture.md
│
├── src/
├── tests/
├── .gitignore
├── .env.example
├── README.md
└── LICENSE
```

<div dir="rtl">

این ساختار برای پروژه‌های کوچک الزام‌آور نیست؛ هدف آن ایجاد یک نقطه شروع منظم برای تیم است.

</div>

---

## 30. Pull Request Template

<div dir="rtl">

برای یکدست شدن PRهای تیم می‌توان Template ایجاد کرد.

</div>

```markdown
## Description

<!-- Explain what changed -->

## Related Issue

Closes #1

## Changes

- [ ] Added feature
- [ ] Updated documentation
- [ ] Added tests

## Testing

- [ ] Unit tests passed
- [ ] Integration tests passed
- [ ] Manual testing completed

## Checklist

- [ ] Code follows project standards
- [ ] No secrets committed
- [ ] Documentation updated if needed
```

---

## 31. Issue Template

<div dir="rtl">

برای Feature:

</div>

```markdown
## Feature

### Goal

Describe the goal.

### Requirements

- Requirement 1
- Requirement 2

### Acceptance Criteria

- [ ] Requirement 1 implemented
- [ ] Requirement 2 implemented
- [ ] Tests added
- [ ] Documentation updated
```

<div dir="rtl">

برای Bug:

</div>

```markdown
## Bug

### Description

Describe the problem.

### Steps to Reproduce

1. Step one
2. Step two
3. Step three

### Expected Behavior

Describe expected behavior.

### Actual Behavior

Describe actual behavior.

### Environment

- Python:
- Django:
- OS:

### Acceptance Criteria

- [ ] Bug is fixed
- [ ] Regression test added
```

---

## 32. `.gitignore` و Secretها

<div dir="rtl">

فایل PDF به‌درستی روی جلوگیری از Commit شدن فایل‌هایی مانند `.env` و `node_modules/` تأکید می‌کند.

نمونه مناسب برای پروژه Python/Django:

</div>

```gitignore
# Environment
.env
.env.*
!.env.example

# Python
__pycache__/
*.py[cod]
*.pyo

# Virtual environment
.venv/
venv/

# Django
db.sqlite3
staticfiles/
media/

# IDE
.vscode/
.idea/

# Node
node_modules/

# OS
.DS_Store
Thumbs.db
```

<div dir="rtl">

`.gitignore` جایگزین Secret Management نیست. اگر Secret قبلاً Commit شده باشد، صرفاً اضافه کردن آن به `.gitignore` Secret را از History حذف نمی‌کند و باید Credential افشاشده را Rotate/Revoke کرد.

</div>

---

## 33. GitHub Actions — نکات امنیتی

<div dir="rtl">

در Workflowهای حساس بهتر است Permissionهای `GITHUB_TOKEN` حداقل مقدار لازم را داشته باشند.

نمونه:

</div>

```yaml
permissions:
  contents: read
```

<div dir="rtl">

همچنین در Workflowهایی که از Actionهای Third-party استفاده می‌کنند، بررسی Source و نسخه Action اهمیت دارد.

برای پروژه‌های حساس، Pin کردن Actionها به Commit SHA می‌تواند امنیت Supply Chain را افزایش دهد.

</div>

---

## 34. Checklist پروژه GitHub

<div dir="rtl">

### Repository

</div>

```text
[ ] README.md
[ ] LICENSE
[ ] .gitignore
[ ] .env.example
[ ] Topics
[ ] Description
[ ] Branch rules / rulesets
```

<div dir="rtl">

### Project Management

</div>

```text
[ ] Issues
[ ] Labels
[ ] Milestones
[ ] Projects
[ ] Assignees
[ ] Issue templates
```

<div dir="rtl">

### Pull Requests

</div>

```text
[ ] PR template
[ ] Code Review
[ ] Required approvals
[ ] Required CI checks
[ ] Squash merge policy
```

<div dir="rtl">

### CI/CD

</div>

```text
[ ] GitHub Actions
[ ] Tests
[ ] Lint
[ ] Formatting
[ ] Build
[ ] Deployment
```

<div dir="rtl">

### Security

</div>

```text
[ ] Dependabot
[ ] Secret scanning
[ ] Push protection
[ ] Code scanning
[ ] Dependency review
[ ] Least privilege
[ ] Secret rotation
```

---

## 35. خلاصه مهم‌ترین قابلیت‌ها

<div dir="rtl">

| قابلیت | کاربرد اصلی |
|---|---|
| Repository | نگهداری کد و فایل‌های پروژه |
| Branch | توسعه مستقل |
| Commit | ثبت تغییرات |
| Issue | مدیریت Task و Bug |
| Label | دسته‌بندی کارها |
| Milestone | گروه‌بندی کارها در یک هدف/نسخه |
| Project | مدیریت Workflow تیم |
| Pull Request | Review و Merge |
| Actions | CI/CD و Automation |
| Secrets | نگهداری مقادیر حساس برای Workflow |
| Releases | انتشار نسخه |
| Tags | علامت‌گذاری نسخه یا نقطه مشخص |
| Pages | میزبانی Static Website |
| Discussions | گفت‌وگوی پروژه |
| CODEOWNERS | تعیین مسئول Review قسمت‌های کد |
| Dependabot | مدیریت Dependency و آسیب‌پذیری‌ها |
| Code Scanning | تحلیل امنیتی کد |
| Secret Scanning | شناسایی Secret |
| Rulesets | اعمال قوانین روی Branch/Tag |
| Codespaces | محیط توسعه ابری |
| GitHub CLI | مدیریت GitHub از Terminal |
| Copilot | کمک توسعه مبتنی بر AI |

</div>

---

## 36. منابع و مراجع

<div dir="rtl">

### محتوای پایه

این سند بر اساس PDF ارائه‌شده با عنوان **GitHub Ultimate Tricks and Tips Cheatsheet FA** تهیه شده است. PDF شامل ترفندهای URL، میانبرها، Search، Repository، Pull Request، GitHub Actions، Secrets، Pages و ابزارهای AI است. fileciteturn0file0L2-L20

بخش‌های Search، Repository، AI و Pull Request نیز از محتوای همان PDF استخراج و توسعه داده شده‌اند. fileciteturn0file0L48-L82 fileciteturn0file0L85-L122

بخش GitHub Actions، Secrets، Pages و `.gitignore` نیز بر اساس محتوای PDF پایه‌گذاری شده است. fileciteturn0file0L125-L138

### مستندات رسمی GitHub

- GitHub Security Features:
  https://docs.github.com/en/code-security/getting-started/github-security-features

- Repository Rulesets:
  https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets/available-rules-for-rulesets

- Issue و Pull Request Search:
  https://docs.github.com/en/issues/tracking-your-work-with-issues/using-issues/filtering-and-searching-issues-and-pull-requests

- GitHub Secret Types:
  https://docs.github.com/en/code-security/reference/secret-security/secret-types

- Repository Roles:
  https://docs.github.com/en/organizations/managing-user-access-to-your-organizations-repositories/managing-repository-roles/repository-roles-for-an-organization

</div>

---

<div dir="rtl">

## نکته نهایی

این فایل عمداً فقط یک Cheatsheet ساده نیست. محتوای PDF اولیه حفظ شده و در کنار آن، قابلیت‌هایی که برای **مدیریت حرفه‌ای Repository، کار تیمی، Code Review، CI/CD و Security** اهمیت بیشتری دارند نیز اضافه شده‌اند.

برای پروژه‌ای مانند `library-management-advance`، مهم‌ترین قسمت‌هایی که بهتر است واقعاً استفاده شوند عبارت‌اند از:

**Issues → Milestones → Projects → Branches → Commits → Pull Requests → Code Review → GitHub Actions → Rulesets → Security**

این زنجیره، GitHub را از یک محل صرفاً برای نگهداری کد به یک سیستم کامل برای مدیریت چرخه توسعه نرم‌افزار تبدیل می‌کند.

</div>
