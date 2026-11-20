# Open-source church event registration

Online sign-up for church events: your own questions, seat limits that hold, a waitlist, confirmation emails with a QR code, and a check-in desk on a phone at the door.

This repository is the **Event Registration** edition of [Church4Christ](https://github.com/leveo/church4christ), an open-source
church management system and website. It contains no separate code: the quick start below
installs Church4Christ v1.7.0 with only the Event Registration features switched on (Registration).
Everything else stays off until you turn it on.

**[Try the live demo](https://demo.church4christ.org/en/sandbox)** · [Main repository](https://github.com/leveo/church4christ) · [Setup guide](https://github.com/leveo/church4christ/blob/v1.7.0/docs/setup.md)

## What you get

- **A public page for every event.** Visitors see the date, the place, and the seats left. You choose when an event appears, when sign-up opens, and when it closes.
- **The questions you need.** Build each event's form by dragging questions into order: dropdowns, yes/no, numbers, and paragraphs. Ask some once and some for each person, and show a question only when an earlier answer fits.
- **Families and groups sign up together.** One sign-up can cover several people, up to a limit you set, and they take seats together. Ticket types such as Adult and Child can each have their own limit.
- **Seat limits that hold, and a waitlist.** The last seat never goes to two people. When an event is full, people can join the waitlist and move up when seats free up.
- **Guests need no account.** A guest confirms their email with a short code before the sign-up is saved. Everyone gets a confirmation email with a QR code, a calendar file, and a private link to change or cancel.
- **A back office for each event.** Numbers at a glance, a roster you can search and filter, answer tallies, approval when you want it, sign-ups added by hand, possible duplicates, reminder emails, and one message to everyone who registered. Download the roster as a spreadsheet.
- **A check-in desk on a phone.** Volunteers find people by name or scan the QR code, and several phones stay in step. Print name badges and a sign-in sheet.
- **Access for one event only.** Give a volunteer a role on one event, such as the check-in desk, without opening the rest of the admin area.
- **12 interface languages**, including English and Chinese. Event titles, descriptions, and questions can be written in every language your site offers.

## Screenshots

![The public list of events, each marked Free](https://raw.githubusercontent.com/leveo/church4christ/v1.7.0/docs/images/registration/public-list.png)

![A sign-up form for a family, with seats left and the event's own questions](https://raw.githubusercontent.com/leveo/church4christ/v1.7.0/docs/images/registration/party-form.png)

![The form builder, with a question shown only when an earlier answer fits](https://raw.githubusercontent.com/leveo/church4christ/v1.7.0/docs/images/registration/builder-questions.png)

![An event's back office: seats, waitlist, check-ins, answer tallies, and the roster](https://raw.githubusercontent.com/leveo/church4christ/v1.7.0/docs/images/registration/backoffice-overview.png)

## Try the live demo

Open the [public sandbox](https://demo.church4christ.org/en/sandbox). Open **Register** in the site menu to see the public event list, then choose **Administrator** and open **Registration** in the admin menu. Each event has a **Check-in desk** button. All data is fictional and resets every night.

## Quick start

You need [Git](https://git-scm.com/) and [Node.js](https://nodejs.org/) 22.22.1 or newer.
These commands work in macOS and Linux terminals and in Windows PowerShell.

```bash
git clone --depth 1 --branch v1.7.0 https://github.com/leveo/church4christ.git my-church
cd my-church
npm ci
npm run onboard -- --preset event-registration
```

`npm run onboard` opens a local form in your browser for your church's name, colors, logo,
and first administrator, with the Event Registration features already checked. Save the form, press
Ctrl+C in the terminal, then apply it and start the site:

```bash
node scripts/setup/index.mjs --preferences .church/preferences.json --yes --dry-run
node scripts/setup/index.mjs --preferences .church/preferences.json --yes
npm run dev
```

Prefer the terminal only? Run `npm run setup -- --mode local --preset event-registration`
instead of the form and answer the prompts.

Open the address the installer prints (usually `http://localhost:4321`). On your own
computer, sign-in links print to the terminal instead of being emailed.

## Good to know

- This edition runs on the default Cloudflare D1 database, where every event is free. Paid events need a Supabase (PostgreSQL) database and a Stripe account. If you plan to charge, install with Supabase from the start (`npm run setup -- --mode local --preset event-registration --backend supabase`); an existing D1 site is not moved to Supabase automatically.
- Rooms, tables, and small groups for retreats and banquets come from the separate Event Logistics feature. It is off here; turn it on later in **Settings → Modules**.
- Confirmation, reminder, and sign-in emails need an email provider when deployed; on your own computer they print to the terminal.

## Grow into the full system

This is the complete Church4Christ codebase with a focused starting point. When you are
ready, an administrator can turn on more features (sermons, events, volunteers, groups,
check-in, and more) in **Settings → Modules**, without reinstalling. Upgrades follow the
main repository's [upgrade guide](https://github.com/leveo/church4christ/blob/v1.7.0/docs/upgrade.md).

## Learn more

- [Event registration](https://github.com/leveo/church4christ/blob/v1.7.0/docs/features/registration.md)
- [Rooms, tables, and small groups (optional add-on)](https://github.com/leveo/church4christ/blob/v1.7.0/docs/features/event-logistics.md)
- [Supabase and Stripe for paid events](https://github.com/leveo/church4christ/blob/v1.7.0/docs/supabase-setup.md)
- [Putting it online with Cloudflare](https://github.com/leveo/church4christ/blob/v1.7.0/docs/setup.md)

## 中文简介

### 开源教会活动报名系统

教会活动的网上报名：自订报名问题、名额上限、候补名单、附二维码的确认邮件，以及门口用手机操作的报到台。

- 每个活动都有公开页面，可设定何时显示、何时开放报名、何时截止。
- 拖拽排序的报名表：下拉、是/否、数字、段落，可按条件显示问题。
- 一次报名可包含全家或多人，并可设定票种与各自名额。
- 名额不会超卖；额满后可加入候补名单，有空位时自动递补。
- 访客无需账号，用邮箱验证码确认；确认邮件附二维码、日历文件和修改/取消的私人链接。
- 每个活动的后台：数据总览、名单搜索与筛选、审核、手动添加、群发邮件、导出表格。
- 手机报到台：按姓名查找或扫描二维码，多部手机同步；可打印名牌和签到表。
- 支持 12 种界面语言（含中英文）。

本仓库是 [Church4Christ](https://github.com/leveo/church4christ) 的单一功能版本，不包含另外的代码。按上面的快速开始安装后，
得到的是完整的 Church4Christ v1.7.0，只预先开启了这一组功能；以后可以在「设置 → 模块」里开启更多功能。

## Questions and issues

Please open issues and questions in the [main repository](https://github.com/leveo/church4christ/issues), where all the code
lives. Report security problems privately through its
[security advisories](https://github.com/leveo/church4christ/security/advisories/new).

## License

[GNU GPL v3](LICENSE), the same license as Church4Christ.
