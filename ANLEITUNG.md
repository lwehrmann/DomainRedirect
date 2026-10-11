# Weiterleitung pi.getrollt-wird.net → jump.getrollt-wird.net:8429

Kostenlos über GitHub Pages, mit echtem HTTPS auf Port 443.

## 1. Repository anlegen
1. Auf github.com einloggen → oben rechts **+** → **New repository**
2. Name z. B. `pi-weiterleitung`, **Public** (GitHub Pages ist im kostenlosen Konto nur für öffentliche Repos verfügbar – es steht ja nur die Weiterleitung drin)
3. **Create repository**
4. Auf der leeren Repo-Seite: **uploading an existing file** → die drei Dateien `index.html`, `404.html`, `CNAME` hineinziehen → **Commit changes**

## 2. GitHub Pages einschalten
1. Im Repo: **Settings → Pages**
2. *Source*: **Deploy from a branch**, Branch **main**, Ordner **/ (root)** → **Save**
3. *Custom domain*: steht schon `pi.getrollt-wird.net` drin (kommt aus der Datei `CNAME`)

## 3. DNS bei Hetzner
In der Zone `getrollt-wird.net` einen Eintrag anlegen:

| Typ | Name | Wert |
|---|---|---|
| CNAME | `pi` | `DEIN-GITHUB-NAME.github.io.` |

## 4. HTTPS aktivieren
Nach einigen Minuten (bis ~1 Stunde) zeigt **Settings → Pages** „DNS check successful“.
Dann **Enforce HTTPS** anhaken. Fertig: `pi.getrollt-wird.net` leitet weiter.

## 5. Empfohlen: Domain bei GitHub verifizieren
Verhindert, dass jemand anders deine Subdomains für eigene GitHub-Pages-Seiten nutzen kann.
1. GitHub: Profilbild → **Settings → Pages** (Konto-Einstellungen, nicht Repo) → **Add a domain** → `getrollt-wird.net`
2. GitHub zeigt einen **TXT-Eintrag** (`_github-pages-challenge-…`) → bei Hetzner anlegen → **Verify**

## Anderer Name?
Datei `CNAME` ändern (z. B. `getrollt-wird.net`) und den DNS-Eintrag entsprechend anlegen.
Für die **Hauptdomain** ohne Subdomain braucht es statt CNAME vier A-Einträge auf die GitHub-IPs (siehe GitHub-Hilfe „Managing a custom domain“).
