<div align="center">

<h1>Self Host Layer</h1>

<p><strong>The self-hosted Vercel, on a $5 server you own. No Docker.</strong></p>

<p>Push to GitHub and your app is live with HTTPS.<br/>Domains, databases, backups and alerts from a web panel that runs on your own server.</p>

<p>
<a href="https://selfhostlayer.com">Website</a> ·
<a href="https://selfhostlayer.com/docs">Docs</a> ·
<a href="#quick-start">Quick start</a> ·
<a href="CONTRIBUTING.md">Contributing</a>
</p>

<p>
<img alt="License: MIT" src="https://img.shields.io/badge/license-MIT-blue">
<img alt="Runs on Ubuntu and Debian" src="https://img.shields.io/badge/runs%20on-Ubuntu%20%7C%20Debian-orange">
<img alt="No Docker" src="https://img.shields.io/badge/docker-not%20needed-lightgrey">
<img alt="GitHub stars" src="https://img.shields.io/github/stars/mddanishyusuf/selfhostlayer?style=social">
</p>

</div>

```sh
curl -fsSL https://get.selfhostlayer.com | bash
```

<p align="center">
  <img src=".github/assets/hero-overview.png" alt="A project's overview in the Self Host Layer panel: status, runtime, memory, sandbox score, the live site and CPU and memory charts" width="100%">
</p>

## 🇲🇲 မြန်မာလို အကျဉ်းချုပ်

**Self Host Layer ဆိုတာ ကိုယ်ပိုင် Vercel ပါ** — ကိုယ့်ရဲ့ $5 VPS ပေါ်မှာ run တဲ့
self-hosted platform တစ်ခု။ Docker မလိုပါဘူး။ GitHub ကို push လုပ်လိုက်တာနဲ့
app က HTTPS နဲ့ live ဖြစ်သွားတယ်။ Domain, database, backup, alert တွေကို
ကိုယ့် server ပေါ်က web panel ကနေ စီမံလို့ရတယ်။

### ဘာလို့ သုံးတာလဲ

- **Transfer limit မရှိဘူး။** Vercel free plan ရဲ့ 10 GB Fast Origin Transfer
  limit လို ကန့်သတ်ချက် မရှိဘူး — ကိုယ့် server, ကိုယ့် bandwidth။
- **Push လုပ်ရင် deploy အလိုအလျောက် ဖြစ်တယ်။** Blue/green deploy နဲ့
  downtime မရှိဘူး၊ တစ်ချက်နှိပ်ရုံနဲ့ အရင် version ကို rollback လုပ်လို့ရတယ်။
- **ဘာမှ ဖုံးကွယ်မထားဘူး။** App တိုင်းက သာမန် folder တစ်ခု၊ Linux user တစ်ယောက်၊
  systemd unit တစ်ခု၊ Caddy site တစ်ခု — panel ကို ဖြုတ်လိုက်ရင်တောင်
  app တွေက ဆက်ပြီး run နေမယ်။
- **ဘေးကင်းအောင် လုပ်ထားတယ်။** App တိုင်းက သူ့ user သူ့ memory limit နဲ့
  sandboxed ဖြစ်ပြီး run တယ်၊ တစ်ခုက နောက်တစ်ခုကို ဖတ်လို့မရဘူး၊ နှေးအောင်လည်း
  လုပ်လို့မရဘူး။

### လိုအပ်ချက်

Ubuntu 24.04 / 26.04 ဒါမှမဟုတ် Debian 12 server အသစ် တစ်လုံး၊ RAM 1 GB
အနည်းဆုံး၊ disk အလွတ် 10 GB၊ port 80 နဲ့ 443 ပွင့်နေရမယ်။

### အမြန်စတင်နည်း

**၁။ Install လုပ်ပါ။** Server ထဲကို root နဲ့ SSH ၀င်ပြီး:

```sh
curl -fsSL https://get.selfhostlayer.com | bash
```

မိနစ်အနည်းငယ်ကြာပြီး panel လိပ်စာနဲ့ တစ်ခါသုံး setup token (24 နာရီ သက်တမ်း)
ပြပေးလိမ့်မယ်။

**၂။ အကောင့် ဖွင့်ပါ။** လိပ်စာကို ဖွင့်ပြီး token ကို ထည့်၊ email နဲ့ password
ရွေးပြီး two-factor sign-in ဖွင့်ပါ။ လိပ်စာမှာ Let's Encrypt certificate
အဆင်သင့် ပါပြီးသား။

**၃။ GitHub ချိတ်ပါ။** **New project → Connect GitHub** ကို နှိပ်ပါ။ Panel က
ကိုယ်ပိုင် GitHub App တစ်ခု ဆောက်ပေးပြီး ဘယ် repo တွေကို မြင်နိုင်မလဲ ကိုယ်တိုင်
ရွေးလို့ရတယ်။

**၄။ Repo ကို import လုပ်ပါ။** Repo ကို ရွေးလိုက်တာနဲ့ framework, package
manager, build နဲ့ start command တွေကို အလိုအလျောက် သိပေးတယ်။ Environment
variable တွေ ထည့်ပြီး **Deploy** နှိပ်ပါ — တစ်မိနစ်အတွင်း
`https://<app>.<ip>.sslip.io` မှာ live ဖြစ်သွားတယ်။

**၅။ ကိုယ့် domain ထည့်ပါ** (မဖြစ်မနေ မဟုတ်)။ Project ရဲ့ **Domains** မှာ
`example.com` ကို ထည့်ပါ။ DNS မှန်ကြောင်း စစ်ပြီး HTTPS နဲ့ ပြောင်းပေးတယ်။

အဲဒီနောက်ပိုင်း branch ကို push လုပ်တိုင်း အလိုအလျောက် deploy ဖြစ်သွားမယ်။

> Installer ကို ထပ်ပြီး run လို့ရတယ် — စစ်ဆေးပြီး ပြင်ပေးတယ်၊ setting တွေ
> မပျက်ဘူး။ အသေးစိတ်: [docs/install.md](docs/install.md)။

### ပါဝင်တဲ့ အရာတွေ

- **Push to deploy** — Next.js, Vite, Nuxt, Astro, Remix, Express နဲ့ static site တွေ
- **Domain နဲ့ HTTPS** — ကိုယ့် domain, certificate အလိုအလျောက် သက်တမ်းတိုး
- **Database** — Postgres, MySQL (MariaDB), MongoDB, Redis, SQLite (Docker မလို)
- **Backup** — စာဝှက်ထားပြီး S3/R2/B2 ကို တင်တယ်၊ တစ်ချက်နှိပ်ရုံနဲ့ ပြန်ယူလို့ရတယ်
- **Alert** — deploy fail ရင်၊ app crash-loop ဖြစ်ရင်၊ disk/certificate ပြဿနာရှိရင် Telegram/Discord/webhook/email ပို့တယ်
- **Cron job, background worker, WordPress/Ghost** — တစ်ချက်နှိပ်ရုံနဲ့ ရတယ်
- **`layer` command** — `layer ps`, `layer logs myapp -f`, `layer update`, `layer repair`

အသေးစိတ် အင်္ဂလိပ် docs: [docs/](docs/) (ဒါမှမဟုတ် [selfhostlayer.com/docs](https://selfhostlayer.com/docs))။

### ဒီ fork အကြောင်း

ဒါက [upstream](https://github.com/mddanishyusuf/selfhostlayer) ရဲ့ fork ဖြစ်ပြီး
ကိုယ့် VPS ပေါ်မှာ စမ်းသုံးဖို့ သိမ်းထားတာပါ။ Upstream နဲ့ ကွာခြားချက် တစ်ခုပဲ ရှိတယ်:
`installer/lib/release.sh` မှာ release folder တွေကို `chmod -R a+rX` လုပ်ပေးထားတယ်
— မဟုတ်ရင် panel က WorkingDirectory ထဲ ၀င်လို့ မရဘဲ စတင်မှာ fail တယ်
(permission error)။

## Why

Vercel is lovely until the bill. Docker-based panels want a bigger server and hide your apps inside containers. Self Host Layer does what you'd do by hand (`git pull`, install, build, restart, a web server config, a certificate), done properly:

- **More apps per dollar.** No Docker. The panel idles at about 130 MB, so a 1 GB server runs many small apps.
- **Nothing hidden, no lock-in.** Every app is a plain folder, a Linux user, a systemd unit and a Caddy site you can read. Remove the panel and your apps keep running.
- **Safe by default.** Each app runs sandboxed as its own user with its own memory limit, so one app can't read or slow down another.

## Quick start

**You need** a fresh server with Ubuntu 24.04, Ubuntu 26.04 or Debian 12 (x86_64 or arm64), 1 GB RAM or more, 10 GB free disk, and ports 80 and 443 open. Any VPS works: Hetzner, DigitalOcean, Vultr, Linode…

**1. Install.** SSH in as root and run:

```sh
curl -fsSL https://get.selfhostlayer.com | bash
```

It takes a few minutes and ends with your panel's address and a one-time setup token:

```
┌──────────────────────────────────────────────────────────────┐
│  Self Host Layer is ready
│
│  Open:         https://203-0-113-7.sslip.io
│  Setup token:  ••••••••••••••••
│  (valid 24h, works once; re-run the installer for a new one)
└──────────────────────────────────────────────────────────────┘
```

**2. Create your account.** Open the address, paste the token, pick an email and password, and turn on two-factor sign-in. The address already has a real Let's Encrypt certificate.

**3. Connect GitHub.** Click **New project → Connect GitHub**. The panel creates a GitHub App that only you own, and you choose which repositories it can see.

**4. Import a repo.** Pick a repository. The framework, package manager, build and start commands are detected for you; change anything you like, add environment variables, then **Deploy**. A minute later it's live at `https://<app>.<your-ip>.sslip.io`.

**5. Add your domain** (optional). In the project's **Domains**, add `example.com`. The panel shows the DNS record to create, checks that it points at your server, then switches over with HTTPS.

From now on, every push to your branch deploys by itself. That's it.

> Running the installer again is safe: it checks and repairs everything and keeps your settings. Every flag, what it changes on the server, and how to update or remove it: [docs/install.md](docs/install.md).

## Features

<table>
<tr>
<td width="50%" valign="top">

**Push to deploy**<br/>
Every push builds and goes live with no downtime (blue/green), with one-click rollback. Next.js, Vite, Nuxt, Astro, Remix, Express and static sites, detected for you.

</td>
<td width="50%" valign="top">

**Domains and HTTPS**<br/>
Your own domains, checked through DNS before they go live, with certificates that renew themselves. Free `<app>.<ip>.sslip.io` addresses out of the box.

</td>
</tr>
</table>

<img src=".github/assets/feature-projects.png" alt="The Projects page: each project's latest deployment, RAM and CPU, and status" width="100%">

<img src=".github/assets/feature-domains.png" alt="The Domains page: every project's domains and their status" width="100%">

<table>
<tr>
<td width="50%" valign="top">

**Databases, no Docker**<br/>
Postgres, MySQL (MariaDB), MongoDB, Redis and SQLite, a separate login per app, with a built-in data viewer.

</td>
<td width="50%" valign="top">

**Backups**<br/>
Encrypted, to any S3-compatible bucket (S3, R2, B2), with SQLite checked and every database dumped. Restore in one click.

</td>
</tr>
</table>

<img src=".github/assets/feature-databases.png" alt="The Databases page: Postgres, MySQL, Redis and SQLite with their status" width="100%">

<table>
<tr>
<td width="50%" valign="top">

**Logs and usage**<br/>
Live build and app logs, every request, and CPU and memory charts for each app and the whole server.

</td>
<td width="50%" valign="top">

**Alerts**<br/>
Telegram, Discord, a webhook or email when a deploy fails, an app crash-loops, or a disk or certificate needs attention.

</td>
</tr>
</table>

<img src=".github/assets/feature-requests.png" alt="A project's request log: time, status, path, duration, size and client" width="100%">

<img src=".github/assets/feature-alerts.png" alt="The Alerts page: an open disk alert and the channels to send alerts to" width="100%">

**And also:** cron jobs as systemd timers · background workers and one-off commands · private files that aren't in Git · WordPress and Ghost sites in one click · one panel deploying to several servers · two-factor sign-in, an audit log, and locking the panel to your IP or Tailscale · one-click updates.

## The `layer` command

Everything is a plain systemd unit, so you can always SSH in. The `layer` command is a thin, readable wrapper:

```sh
layer ps               # every app, its live color and domains
layer logs myapp -f    # follow an app's output (journalctl underneath)
layer score myapp      # the app's sandbox score from systemd
layer update           # update the panel, agent and CLI; apps keep running
layer repair           # put back anything edited by hand
layer access reset     # locked out of the panel? this lets you back in
```

All commands: [docs/cli.md](docs/cli.md).

## How it works

```
             your browser                 GitHub
                  │                         │ webhooks, tarballs
                  ▼                         ▼
   ┌───────────────────────── your server ──────────────────────────┐
   │  Caddy  ──►  panel (Next.js, user `layer`)                     │
   │    │              │ unix socket, allowlisted actions only      │
   │    │              ▼                                            │
   │    │         agent (root): builds, units, Caddy, databases     │
   │    ▼                                                           │
   │  app-a@blue   app-b@green   …   each its own user, sandboxed   │
   │  a systemd unit with a memory limit, data in /srv/apps/<app>   │
   └────────────────────────────────────────────────────────────────┘
```

- **The panel** is a Next.js app that runs as an unprivileged user and listens only on a unix socket behind Caddy.
- **The agent** is the only thing that runs as root. It accepts a fixed list of actions with strict validators (`packages/protocol`) and writes plain systemd units and Caddy files.
- **Each app** is built in a sandbox, then runs as its own Linux user under systemd with a memory limit. A deploy starts the new color, checks it's healthy, then switches traffic.

The full security model, including the honest limits: [docs/security.md](docs/security.md).

## Docs

| | |
|---|---|
| [Install](docs/install.md) | Requirements, the one command, updating, repairing, removing |
| [The panel, page by page](docs/panel.md) | What every page does |
| [Servers](docs/servers.md) | One panel, several servers |
| [Sites](docs/sites.md) | WordPress and Ghost |
| [The `layer` command](docs/cli.md) | Every CLI command and the raw command underneath |
| [Security model](docs/security.md) | Sandboxing, secrets, and the honest limits |
| [Moving an app from pm2](docs/moving-from-pm2.md) | Step by step, with your data |

The same docs, easier to read: [selfhostlayer.com/docs](https://selfhostlayer.com/docs).

## Develop

<details>
<summary>Run it locally, test it in a VM, and the repo layout</summary>

<br/>

Needs Node 24 (`.nvmrc`) and yarn 1. TypeScript runs directly through Node's type stripping, with no build step in development.

```sh
yarn install
yarn test                 # vitest
yarn typecheck            # tsc, no emit
LAYER_FAKE_AGENT=1 yarn --cwd panel dev   # the panel on your machine, with a fake agent
yarn build:installer      # → dist/install.sh (one file)
bash scripts/build-release.sh   # → dist/layer-<version>.tar.gz
```

| Path | What |
|---|---|
| `installer/` | `install.sh` plus `lib/*.sh`, bundled into one file by `scripts/build-installer.sh` |
| `agent/` | The root helper: allowlisted actions over a unix socket, templates for units and Caddy files |
| `packages/protocol/` | The action allowlist, validators and the agent client, shared by the agent, CLI and panel |
| `packages/cli/` | The `layer` command |
| `panel/` | The Next.js panel |
| `system/` | systemd units for the agent and the panel |
| `docs/` | User docs |

**Test on a real Ubuntu in a local VM.** Install [Multipass](https://canonical.com/multipass) (`brew install --cask multipass`), then:

```sh
scripts/dev-vm.sh up        # Ubuntu 24.04 VM, 2 CPU / 2 GB RAM, like a small VPS
scripts/dev-vm.sh release   # build a release and run the real installer with it
scripts/dev-vm.sh verify    # check the server state the installer promises
scripts/dev-vm.sh e2e       # agent and blue/green end-to-end tests
scripts/dev-vm.sh ui        # browser tour of the panel: setup, 2FA, sign in
scripts/dev-vm.sh lint      # shellcheck every script
scripts/dev-vm.sh reset     # start again from a fresh box
```

`LAYER_VM_IMAGE=26.04` tests the other Ubuntu release. The VM has no public address, so real Let's Encrypt certificates still need a real server.

To try a local build on a server: run `bash scripts/build-installer.sh && bash scripts/build-release.sh 0.1.0`, copy `dist/install.sh` and the tarball over, and run `bash install.sh --from-tarball layer-0.1.0.tar.gz` there.

</details>

## Contributing

Issues and pull requests are welcome. Please read [CONTRIBUTING.md](CONTRIBUTING.md) first; for anything big, open an issue before writing code.

Found a security problem? Please report it privately: [SECURITY.md](SECURITY.md).

If Self Host Layer is useful to you, a ⭐ helps other people find it.

## License

[MIT](LICENSE) © MVP Stack LLC. Use it, change it and ship it anywhere, commercially or not. The font files in `panel/app/fonts/` are licensed separately and aren't covered (see [LICENSE](LICENSE)).
