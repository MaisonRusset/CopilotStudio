
# Copilot Studio – Manifestes de compétences (MaisonRusset)

Ce paquet contient des **manifestes JSON** pour ajouter des compétences à un agent **Microsoft Copilot Studio**, utilisant **Microsoft Graph** avec **permissions déléguées**.

## Structure
- `manifests/Mail_ReadWrite_V3.json` – Courriels (lecture/écriture + recherche)
- `manifests/Calendar_Read_V2.json` – Calendrier (événements)
- `manifests/SharePoint_Files_V2.json` – Fichiers récents + listing site
- `manifests/Teams_Chat_Read_V2.json` – Chats et messages Teams

## Scopes requis (Entra ID → API permissions → Grant admin consent)
- Mail: `Mail.ReadWrite`, `Mail.Send`, `User.Read`
- Calendar: `Calendars.Read`
- SharePoint/OneDrive: `Files.Read`, `Sites.Read.All`
- Teams (chats): `Chat.Read`

## Import dans Copilot Studio
1. Ouvrir **Copilot Studio → Agent → Compétences → Ajouter une compétence**.
2. Coller l’URL **RAW** du manifeste (GitHub) :
   - Mail (exemple) :  
     `https://raw.githubusercontent.com/MaisonRusset/CopilotStudio/main/manifests/Mail_ReadWrite_V3.json`
3. Suivant → Valider → Publier l’agent.
4. Tester dans Teams/M365:
   - “Recherche les courriels contenant *facture*”
   - “Montre mes prochains événements”
   - “Liste mes fichiers récents”
   - “Montre les derniers messages du chat XYZ”

## Notes
- Utiliser toujours **raw.githubusercontent.com** (pas l’URL “blob”).
- Les actions consomment des **Copilot Credits** (packs/PAYG). Si user a **M365 Copilot**, plusieurs scénarios internes sont **zero‑rated**.
- Surveiller la capacité dans **Power Platform Admin Center → Capacités → Copilot Credits**.
