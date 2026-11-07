# Context: Personal admin

_Opgeschoonde versie van de Claude-kennis (7 Nov 2026). Weggelaten: rekening- en hypotheeknummers, rentes, termijnbedragen, pensioenbedragen, adressen._

## Doel
Persoonlijke administratie: money hub (financieel overzicht), documenten op de Synology, foto's, wachtwoord-opruiming.

## Systemen en waar ze staan
- Mac: MacBook Air; Claude-desktopapp moet open zijn voor apparaatwerk. NAS: Synology DS825 en een oudere Synology.
- **Money hub**: Microsoft Money (in Parallels) → QIF-exports in `~/Money Exports` → Mac-adapter `~/MoneyDashboard/adapter` (money_adapter.py + forecast.py) → `snapshot.json` in `~/Library/CloudStorage/SynologyDrive-MoneyDasboard/data` → Docker "money-publisher" op de Synology (allow-listed velden, elke 5 min) → MQTT → HA-apparaat "Money Dashboard". Auto-update via LaunchAgent; logs in `~/Library/Logs`.
- Live koersen: pyscript `money_markets.py` in HA (Yahoo); posities in `/config/money/positions.json`. Wall-panel-weergaven "money" en "cashflow", verborgen voor Raeven.
- Rekeningsoorten: ISA (Trading 212), SIPP (interactive investor), twee Standard Life-pensioenen (handmatig), een DB-pensioen (TUI), hypotheek en spaarrekening bij Nationwide (handmatige `valuations.json`; as_of bijwerken bij nieuwe afschriften).
- **Documenten**: `~/Library/CloudStorage/SynologyDrive-Documents/Documents`, ingedeeld 00 To Sort … 14 Personal & Community, 99 Archive (opgeruimd 23 okt 2026; logs en undo in `99 Archive/_Tidy-up 2026-10-23/`). Nieuwe bestanden datum-eerst benoemen (YYYY-MM-DD …).
- **Foto's**: Apple Photos-bibliotheek op externe schijf "Elements"; backup naar DS825-share "Elements-Backup"; doel: alles in Synology Photos/Immich met AI-sortering. Plan nog concept.

## Regels en voorkeuren
- VERTROUWELIJK; financiële data niet extern delen; geld niet op dashboards die de kinderen zien.
- **Nooit wachtwoorden, sleutels of logins lezen of bewaren. Nooit `secrets.env` of de Gegevens*-bestanden openen.**
- Verplaatsen/hernoemen met undo-log en akkoord; verwijderen alleen met expliciete toestemming.
- Geef one-line Terminal-commando's (base64 one-liners werken).

## Bekende valkuilen
- De VM ziet cloud-only mappen als leeg.
- Claude kan geen Gmail-bijlagen downloaden; de eigenaar slaat ze op.
- Grote NAS-scans: één Terminal-commando, niet via device_bash over SMB.
