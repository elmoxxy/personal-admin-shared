# AGENTS.md: regels voor Claude, ChatGPT en andere assistenten

Project: **Personal admin**. Eigenaar: elmoxy (GitHub `elmoxxy`).

## Begin van elke sessie
1. Haal alle branches op. Lees `docs/CONTEXT.md` en `docs/HANDOFF.md` van de meest recent gepushte branch (niet alleen main), plus het nieuwste bestand in `docs/changes/`.
2. Bekijk open PR's.
3. Geef een status van maximaal 8 regels en vraag waar we aan werken.

## Na elke echte wijziging of beslissing (direct, niet aan het eind van de dag)
1. Branch vanaf de nieuwste stand: `fix/…`, `feat/…` of `docs/…` + datum (JJJJ-MM-DD).
2. Schrijf `docs/changes/JJJJ-MM-DD-onderwerp.md` (volg `TEMPLATE.md`): wat, waarom, voor/na, hoe terugdraaien.
3. Werk `docs/HANDOFF.md` bij (open punten, laatste stand) en voeg een regel toe aan `CHANGELOG.md`.
4. Nieuwe vaste kennis gaat naar `docs/CONTEXT.md`, niet alleen in het eigen geheugen van de assistent.
5. Commit, push, open een PR. **Nooit zelf mergen**; dat doet de eigenaar, of een assistent als de eigenaar daar expliciet om vraagt.
6. Kun je niet pushen: geef de volledige nieuwe tekst van HANDOFF.md en het changes-bestand in codeblokken, zodat de eigenaar ze doorzet.

## Nooit in deze repo
- Wachtwoorden, API-sleutels, tokens, app-wachtwoorden, webhook-URL's, back-up- of encryptiesleutels, inloggegevens.
- Persoonsgegevens en identificerende nummers: BSN, personeelsnummer, rekening-/hypotheeknummers, adressen van derden.
- Brondocumenten: loonstroken, roosters, logboeken, bankafschriften, facturen, bonnen, spreadsheets met bedragen. Die blijven op de Synology; noem alleen het pad.
- Bedragen per persoon of per maand, salarissen, belastinggegevens.
Bij twijfel: weglaten en het de eigenaar vragen.

## Extra voor dit project
Vertrouwelijk. In de repo alleen regels, werkwijze, berekeningsmethodes en open vragen zonder bedragen. Geen artifacts of publieke links met gegevens uit dit project.

Nooit de Gegevens*-wachtwoordbestanden of secrets.env openen. Verplaatsen/hernoemen alleen met undo-log en na akkoord; verwijderen alleen met expliciete toestemming.

## Taal
De eigenaar schrijft Nederlands en Engels; antwoord in de taal van zijn bericht. Documenten in deze repo mogen Nederlands of Engels zijn.

## Andere projecten
Home Assistant: `elmoxxy/home-assistant-shared`. TUI pilot: `elmoxxy/tui-pilot-shared`. Huize Welbergen: `elmoxxy/huize-welbergen-shared`. Personal admin: `elmoxxy/personal-admin-shared`. Hoort iets bij een ander project: zeg dat, en zet het daar (niet hier).
