# SEL-hw1 — Personal Portfolio

> A clean, responsive one-page portfolio website built with **pure HTML, CSS, and JavaScript** — no frameworks, no build step, no dependencies.

This repository contains the first homework for the **Software Engineering Lab** course at **SUT (2026 Summer)**. The goal was to implement a personal portfolio page with a focus on theming, clean code, and a proper Git workflow.

Repository: [github.com/arkadashsiz/SEL-hw1](https://github.com/arkadashsiz/SEL-hw1)

---

## Table of Contents

- [Features](#features)
- [Implementation Report](#implementation-report)
- [Branch Structure & Git Workflow](#branch-structure--git-workflow)
- [Commit History](#commit-history)
- [Getting Started](#getting-started)
- [Deployment (GitHub Pages)](#deployment-github-pages)
- [Live Demo (Frontend Launch)](#live-demo-frontend-launch)
- [Git Theory Questions](#git-theory-questions)
- [Customization](#customization)
- [License](#license)

---

## Features

- **Responsive Layout** — adapts seamlessly to small screens with a collapsible mobile menu.
- **Dark Theme by Default** — with a **light/dark theme toggle** button that persists user preference via `localStorage`.
- **Accessible Markup** — semantic HTML5 elements, ARIA labels, keyboard support, and reduced-motion support.
- **Smooth Scrolling** — for in-page navigation links.
- **CSS Custom Properties** — design tokens for easy theming and maintenance.

---

## Implementation Report

### Phase 1: Project Setup & Git Initialization

1. **Repository Creation:** Cloned the initial repository from `git@github.com:arkadashsiz/SEL-hw1.git`.
2. **Branching Strategy:** Adopted a feature-branch workflow to isolate development. Each new feature was developed in a separate branch and then merged into the `main` branch via Pull Requests.

### Phase 2: Dark Mode Implementation

- **Technology:** Used `data-theme` attribute on the `<html>` element.
- **JavaScript:** Added a `click` event listener to the `#themeToggle` button to toggle between `dark` and `light` values.
- **Persistence:** Integrated `localStorage` so the user's preference is remembered across sessions.
- **CSS Variables:** Defined color tokens in `:root` (dark) and `[data-theme="light"]` (light) for easy switching.

### Phase 3: Visual Improvements & Code Refinements

- **HTML Structure:** Removed duplicate sections (`#home`, `#about`) and ensured a logical hierarchy.
- **CSS Enhancements:** Applied consistent spacing, improved card styling, and made the mobile navigation functional.
- **Code Quality:** Removed redundant code and ensured the project structure aligns with the final version.

---

## Branch Structure & Git Workflow

The repository uses a **feature-branch workflow** to manage development. Below is a summary of all branches identified in the repository:

| Branch Name | Purpose | Status |
| :--- | :--- | :--- |
| `main` | Stable, production-ready branch. Deployed to GitHub Pages. | Active |
| `feature/dark-mode-button` | Implementation of the dark/light theme toggle and related JavaScript logic. | Merged |
| `feature/javascript` | Adding JavaScript features (mobile menu, dynamic year, etc.). | Merged |
| `fix_visual_box` | Hotfix branch for visual improvements (box-sizing, alignment, spacing). | Active |

**Workflow Steps:**

1. Created `feature/dark-mode-button` from `main`.
2. Developed the dark mode feature (HTML, CSS, JS).
3. Opened a **Pull Request (PR)** and merged it back into `main`.
4. Created `fix_visual_box` from `main` for post-merge visual refinements.
5. All changes are tracked with meaningful, atomic commit messages.

---

## Commit History

Below is a summary of the key commits made during this development cycle, based on the repository's history:

| Commit Message | Branch | Description |
| :--- | :--- | :--- |
| `Initial commit` | `main` | Repository setup with LICENSE file. |
| `add readme` | `main` | Initial README file. |
| `add dark mode button` | `feature/dark-mode-button` | Added theme toggle button and JavaScript logic. |
| `improve gitignore` | `fix_visual_box` | Improved .gitignore to exclude IDE and OS files. |
| `finished the java script file and added features` | `main` | Finalized JS features and styling. |

---

## Getting Started

The site is fully static. Simply open `index.html` in a browser, or run a local server:

```bash
npx serve .
# or
python -m http.server 8080
```

Then visit `http://localhost:8080` (or the port shown) in your browser.

---

## Deployment (GitHub Pages)

The project is deployed to **GitHub Pages** directly from the `main` branch. Repository settings: `Settings → Pages → Source: main branch / root`.

**GitHub Pages URL:** https://arkadashsiz.github.io/SEL-hw1/

---

## Live Demo (Frontend Launch)

To view the live, deployed front end, open the link below:

👉 **https://arkadashsiz.github.io/SEL-hw1/**

---

## Git Theory Questions

### پوشه‌ی `.git` چیست؟

پوشه‌ی `.git` قلب هر ریپازیتوری گیت است و همان چیزی است که یک پوشه‌ی معمولی را به یک ریپازیتوری گیت تبدیل می‌کند. تمام اطلاعات لازم برای مدیریت تاریخچه‌ی پروژه در این پوشه ذخیره می‌شود، از جمله:

- **Object database** (`objects/`): شامل تمام blob ها (محتوای فایل‌ها)، tree ها (ساختار پوشه‌ها)، commit ها و tag ها.
- **Refs** (`refs/`): اشاره‌گرهایی به commit ها، شامل برنچ‌ها (`refs/heads`) و تگ‌ها (`refs/tags`).
- **HEAD**: فایلی که مشخص می‌کند کاربر در حال حاضر روی کدام برنچ یا کامیت قرار دارد.
- **Index (Staging Area)**: فایل `index` که وضعیت فعلی stage را نگه می‌دارد.
- **Config**: تنظیمات مربوط به همان ریپازیتوری (`config`).
- **Logs**: تاریخچه‌ی حرکت HEAD و برنچ‌ها (`reflog`).

این پوشه با دستور زیر ساخته می‌شود:

```bash
git init
```

### atomic بودن در atomic commit و atomic pull-request یعنی چه؟

**Atomic commit** یعنی هر کامیت باید تنها یک تغییر منطقی و مستقل را در بر بگیرد؛ یعنی اگر آن کامیت را جدا و به‌تنهایی revert کنیم، پروژه همچنان در وضعیتی سالم و قابل build/اجرا باقی بماند. مخلوط کردن چند تغییر نامرتبط (مثلاً یک باگ‌فیکس و یک فیچر جدید) در یک کامیت، آن را غیر atomic می‌کند.

**Atomic pull-request** به همین منطق در سطح بزرگ‌تر اشاره دارد: هر PR باید یک ویژگی یا تغییر مستقل و کامل را پوشش دهد، به‌گونه‌ای که بتوان آن را جدا از سایر PR ها بررسی (review)، merge یا در صورت نیاز revert کرد، بدون آنکه به بخش‌های دیگر پروژه آسیب بزند.

### تفاوت `fetch`، `pull`، `merge`، `rebase` و `cherry-pick`

- **`git fetch`**: تغییرات جدید را از ریموت دانلود می‌کند و برنچ‌های ریموت‌تراکینگ (مثل `origin/main`) را به‌روز می‌کند، اما هیچ تغییری در برنچ فعلی یا working directory اعمال نمی‌کند.
- **`git pull`**: معادل اجرای `git fetch` و سپس `git merge` (یا با فلگ `--rebase`، معادل `git fetch` + `git rebase`) است؛ یعنی تغییرات ریموت را می‌گیرد و بلافاصله با برنچ فعلی ترکیب می‌کند.
- **`git merge`**: دو برنچ را با ساختن یک **merge commit** جدید (که دو (یا چند) پدر دارد) با هم ترکیب می‌کند و تاریخچه‌ی هر دو برنچ را حفظ می‌کند.
- **`git rebase`**: کامیت‌های یک برنچ را برداشته و آن‌ها را روی نوک برنچ دیگری «بازپخش» می‌کند و در نتیجه یک تاریخچه‌ی خطی و بدون merge commit ایجاد می‌شود؛ اما commit hash های جدید ساخته می‌شوند.
- **`git cherry-pick`**: یک یا چند کامیت خاص را (نه یک برنچ کامل) از جایی دیگر انتخاب کرده و به‌صورت کامیت‌های جدید روی برنچ فعلی اعمال می‌کند، بدون آنکه بقیه‌ی تاریخچه‌ی آن برنچ منتقل شود.

### تفاوت `reset`، `revert`، `restore`، `switch` و `checkout`

- **`git reset`**: اشاره‌گر برنچ فعلی (HEAD) را به یک کامیت دیگر منتقل می‌کند و بسته به حالت (`--soft`, `--mixed`, `--hard`) می‌تواند stage و/یا working directory را هم تغییر دهد. تاریخچه را بازنویسی می‌کند و برای کامیت‌های عمومی/push‌شده خطرناک است.
- **`git revert`**: به‌جای حذف یک کامیت، یک کامیت **جدید** می‌سازد که اثر کامیت مورد نظر را خنثی می‌کند؛ تاریخچه دست‌نخورده باقی می‌ماند، پس برای برنچ‌های عمومی امن‌تر است.
- **`git restore`**: برای بازگرداندن فایل‌ها در working directory یا stage به یک نسخه‌ی مشخص (معمولاً آخرین کامیت) استفاده می‌شود، بدون اینکه برنچ یا HEAD جابه‌جا شود.
- **`git switch`**: مخصوص جابه‌جایی بین برنچ‌ها است (جایگزین بخشی از کاربرد `checkout` برای وضوح بیشتر).
- **`git checkout`**: دستوری چندمنظوره و قدیمی‌تر که هم می‌تواند برنچ عوض کند، هم فایل‌ها را بازگرداند و هم به یک کامیت خاص (حالت detached HEAD) برود؛ به همین دلیل `switch` و `restore` برای شفاف‌سازی این کاربردهای مجزا معرفی شدند.

### منظور از stage یا index چیست؟ دستور `stash` چه کاری می‌کند؟

**Stage (یا Index)** یک ناحیه‌ی میانی بین working directory و object database است. تغییراتی که با `git add` انتخاب می‌شوند، وارد این ناحیه می‌شوند و فقط همان تغییرات هستند که با اجرای `git commit` تبدیل به یک snapshot (کامیت) جدید می‌شوند. این مکانیزم اجازه می‌دهد که تنها بخشی از تغییرات (نه لزوماً همه‌ی فایل‌های تغییر یافته) در یک کامیت قرار بگیرد.

**`git stash`** تغییرات ثبت‌نشده‌ی working directory (و در صورت نیاز stage) را به‌طور موقت کنار می‌گذارد و working directory را به حالت آخرین کامیت برمی‌گرداند، بدون آنکه کامیتی ساخته شود. این تغییرات در یک پشته (stack) ذخیره می‌شوند و بعداً با `git stash pop` یا `git stash apply` قابل بازگردانی هستند؛ کاربرد اصلی آن جابه‌جایی سریع بین کارها (مثلاً تعویض موقت برنچ) بدون از دست دادن تغییرات ناتمام است.

### مفهوم snapshot چیست؟ ارتباط آن با commit چیست؟

برخلاف تصور رایج، گیت تغییرات را به‌صورت **diff** (تفاوت بین نسخه‌ها) ذخیره نمی‌کند، بلکه هر کامیت یک **snapshot** یعنی یک عکس فوری از کل وضعیت پروژه در آن لحظه است. هر commit به یک tree اشاره می‌کند که ساختار کامل دایرکتوری‌ها و فایل‌ها را در آن نقطه از زمان نشان می‌دهد. برای صرفه‌جویی در فضا، اگر فایلی نسبت به کامیت قبلی تغییر نکرده باشد، گیت به همان blob قبلی اشاره می‌کند و آن را دوباره ذخیره نمی‌کند؛ بنابراین snapshot ها به‌صورت مؤثر و بدون تکرار غیرضروری ذخیره می‌شوند. هر کامیت همچنین به کامیت (یا کامیت‌های) پدر خود اشاره می‌کند و به همین ترتیب زنجیره‌ای از snapshot ها، تاریخچه‌ی پروژه را می‌سازد (منبع: [Commits are snapshots, not diffs](https://github.blog/2020-12-17-commits-are-snapshots-not-diffs/)).

### تفاوت local repository و remote repository

- **Local repository**: نسخه‌ای از ریپازیتوری که روی سیستم شخصی توسعه‌دهنده قرار دارد و شامل working directory، staging area و پوشه‌ی `.git` کامل با تمام تاریخچه است. تمام عملیات‌هایی مثل commit، branch، merge و rebase به‌صورت پیش‌فرض به‌صورت محلی و آفلاین انجام می‌شوند.
- **Remote repository**: نسخه‌ای از همان ریپازیتوری که روی یک سرور (مثل GitHub) میزبانی می‌شود و معمولاً به‌عنوان نقطه‌ی اشتراک بین چند توسعه‌دهنده عمل می‌کند. ارتباط بین این دو از طریق دستورهایی مثل `fetch`، `pull` و `push` برقرار می‌شود؛ یعنی تغییرات محلی باید صریحاً با `push` به remote ارسال شوند و تغییرات remote باید با `fetch`/`pull` به local آورده شوند — برخلاف local repository که تغییرات در آن بلافاصله و بدون نیاز به انتقال شبکه‌ای در دسترس است.

---

## Customization

Update the content in `index.html` (name, bio, projects, links), adjust color tokens in the CSS `:root` / `[data-theme="light"]` blocks, and replace any placeholder images or links with your own.

## License

This project is released under the license specified in the `LICENSE` file of the repository.

## Project Address
the project can be found on the web at https://arkadashsiz.github.io/SEL-hw1/
