---
title: Esegui prima Microsoft Teams
author: LaszloSomi
ms.author: lsomi
manager: swerth
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: lsomi
ms.localizationpriority: medium
search.appverid: MET150
description: Usare queste indicazioni per implementare Microsoft Teams come primo carico di lavoro Microsoft 365 o Office 365.
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: f6dba57003aaa58b9d0b72e7e866da261bed578e
ms.sourcegitcommit: 1d990582e2deb5f55ba9adada3e17377f792a141
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2022
ms.locfileid: "64922687"
---
# <a name="roll-out-microsoft-teams-first"></a>Esegui prima Microsoft Teams

Microsoft Teams possono aiutare i dipendenti a rimanere in contatto e collaborare tra loro, soprattutto nell'attuale periodo senza precedenti in cui il lavoro remoto è una realtà dei dipendenti di tutto il mondo. La possibilità di chattare, organizzare video riunioni e collaborare a documenti Office all'interno di Teams può aiutare le aziende a rimanere produttive. Sia che si sia una piccola azienda, una no profit o un'organizzazione di grandi dimensioni, è possibile iniziare a usare Teams come primo carico di lavoro all'interno di Microsoft 365 o famiglia di prodotti Office 365 prima di distribuire altri app Office o servizi.

Questo articolo descrive in dettaglio le considerazioni da fare con l'approccio "Teams First".

> [!IMPORTANT]
> Anche se Teams può essere il primo carico di lavoro distribuito nel cloud dell'organizzazione, la distribuzione di Teams deve far parte della strategia di distribuzione globale del cloud.

Se sono già stati implementati altri servizi di Microsoft 365 o Office 365 e Teams è il prossimo carico di lavoro da implementare anziché il primo, iniziare con [Come implementare Teams](./deploy-overview.md).

## <a name="start-here"></a>Iniziare da qui

Per iniziare a usare Teams Prima distribuzione, è necessario soddisfare almeno alcuni prerequisiti. L'elenco seguente mostra le impostazioni necessarie per l'organizzazione prima di abilitare Teams:

1.  Un Microsoft 365 o un'organizzazione Office 365 configurata con il nome di dominio

2.  Azure Active Directory la connettività (AAD connettersi) o una soluzione di sincronizzazione delle identità cloud simile, con tutti gli attributi necessari sincronizzati con il tenant  
    Per comprendere gli attributi sincronizzati con AAD sincronizzazione, leggere [Azure AD Connessione sincronizzazione: Attributi sincronizzati con Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)

3.  Licenze utente appropriate assegnate per Teams  
    Per informazioni sulle licenze Teams, leggere [Microsoft Teams descrizione del servizio](/office365/servicedescriptions/teams-service-description).

4.  Rete dell'organizzazione preparata per Teams  
    Per informazioni sulla preparazione della rete, vedere [Preparare la rete dell'organizzazione per Teams](prepare-network.md).

5.  Consentire l'accesso di rete a Exchange, SharePoint e OneDrive for Business in Microsoft 365 o Office 365: [Office 365 URL e intervalli di indirizzi IP](/office365/enterprise/urls-and-ip-address-ranges).

> [!NOTE]
> Il provisioning dei tenant creati dopo il 1° settembre 2019 viene eseguito in modalità solo Teams.
> 
> [!IMPORTANT]
> Se è stato distribuito Skype for Business Server e il provisioning del tenant è stato eseguito DOPO il 1° settembre 2019, contattare il supporto per abilitare le funzionalità di coesistenza per Teams. Prima di assegnare Teams licenze a un utente, assicurarsi che i criteri di aggiornamento a livello di organizzazione siano impostati su "Modalità <span class="underline">isola".</span>

## <a name="migration-starting-points"></a>Punti di partenza della migrazione

Il percorso verso Microsoft 365 o Office 365 e le funzionalità disponibili in Teams a seconda del punto di partenza e della presenza di Skype for Business locale o Di Lync Server. Nelle sezioni seguenti vengono descritte in dettaglio le funzionalità di base e le opzioni di configurazione oltre ai prerequisiti precedenti. Gli scenari dei punti di partenza sono stati suddivisi per gli argomenti seguenti:

**Configurazione Teams tenant**: le modalità tenant e utente vengono usate per controllare il comportamento del destinatario. Queste impostazioni possono essere assegnate a livello di tenant o di utente in un'organizzazione. Per altre informazioni, vedere [Coesistenza con Skype for Business](coexistence-chat-calls-presence.md).

**Chat/Comunicazione esterna in Teams**: i servizi di chat fanno riferimento a conversazioni peer-to-peer o di gruppo all'interno e all'organizzazione o esternamente all'organizzazione. La comunicazione esterna viene anche definita federazione in Skype for Business.

**Creare e visualizzare riunioni in Teams**: un utente può sempre creare riunioni online tramite il componente aggiuntivo Outlook Teams ed è disponibile in tutti gli scenari una volta concessa la licenza all'utente. Teams e Skype for Business archiviare le informazioni di calendario nella cassetta postale di Exchange dell'utente. Il server Exchange locale deve essere Exchange Server 2016 CU3 o versione successiva per consentire al client Teams di interagire con la cassetta postale dell'utente. Senza Exchange cassetta postale, l'icona calendario in Teams non verrà visualizzata e l'utente non potrà visualizzare, creare o modificare riunioni nel client Teams.

**Funzionalità di chiamata VoIP/PSTN in Teams**: Le chiamate possono essere VoIP (Voice over IP) o PSTN (Public Switched Telephone Network). La connettività VoIP avviene in modo nativo tra client Teams, mentre la connettività PSTN avviene quando un utente compone un numero di telefono esterno.  

Teams supportano due tipi di connettività PSTN. Piano per chiamate Microsoft, quando Microsoft fornisce un'infrastruttura di telefonia che include il numero di telefono per un utente o la configurazione Routing diretto, in cui il cliente fornisce la connettività di telefonia tramite un controller di frontiera di sessione (SBC) per l'utente Teams.  
Per saperne di più, leggi [Quale piano per chiamate fa per te?](calling-plan-landing-page.md) e [Sistema telefonico Direct Routing](direct-routing-landing-page.md).

**Collaborazione Teams e canali in Teams**: in Teams, i team sono gruppi di persone riunite per lavoro, progetti o interessi comuni. Teams sono costituiti da canali. Ogni canale è basato su un argomento, ad esempio "Eventi del team", il nome di un reparto o solo per divertimento. I canali consentono di organizzare riunioni, avviare conversazioni e lavorare insieme ai file. Durante la collaborazione

**OneDrive for Business (condivisione di file P2P) in Teams**: all'esterno di Teams e canali, Teams gli utenti possono condividere file peer-to-peer usando OneDrive per le aziende o altri programmi di condivisione di file P2P come File Citrix, DropBox, Box e Google Drive. Per OneDrive per le aziende a un utente deve essere assegnata SharePoint licenza online.

**Piattaforma** delle applicazioni: le app forniscono strumenti predefiniti che consentono all'organizzazione di ottenere di più da Teams. Queste app combinano le funzionalità di schede, estensioni di messaggistica, connettori e bot forniti da Microsoft, creati da terze parti o dagli sviluppatori dell'organizzazione.

**Caratteristiche di sicurezza e conformità:** Teams offre un'ampia gamma di informazioni utili per le aree di conformità, tra cui criteri di conservazione, prevenzione della perdita dei dati, eDiscovery e blocco legale per canali, chat e file, ricerca nel log di controllo. Per altre informazioni, vedere [Sicurezza e conformità in Microsoft Teams](security-compliance-overview.md).  

> [!NOTE]
> Le caratteristiche di Advance eDiscovery richiedono licenze E5.

[Confronta le opzioni di licenza](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).

Leggere [Come Exchange e Microsoft Teams interagire](exchange-teams-interact.md) per scoprire quali caratteristiche di conformità sono disponibili nello scenario.

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a>Organizzazioni **<span class="underline">senza</span>** Skype for Business o Lync Server

Questo punto di partenza presuppone che l'organizzazione non utilizzi attualmente Skype for Business o Lync Server e Teams sarà la prima applicazione in Microsoft 365 o Office 365. La tabella seguente descrive in dettaglio le funzionalità di configurazione di alto livello e degli utenti finali per Teams per i servizi di base.

<table>
<thead>
<tr class="header">
<th>Elemento</th>
<th>Note</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Configurazione Teams tenant</td>
<td>Teams modalità Solo, tutte le funzionalità di chat e di chiamata sono disponibili solo Teams.</td>
</tr>
<tr class="even">
<td>Chat/ Comunicazione esterna in Teams</td>
<td><p>Comunicazioni interne (all'interno Microsoft 365 o Office 365 dell'organizzazione) e di chat esterne possibili da Teams.</p>
<p><em>Nota: le voci DNS devono essere configurate per l'accesso esterno. Skype for Business record DNS sono necessari anche se non si dispone di Skype for Business locale o in Microsoft 365 o Office 365, per consentire la federazione con gli ambienti Lync e Skype for Business:<br />
<a href="/office365/enterprise/external-domain-name-system-records">Record Domain Name System esterni</a></em></p></td>
</tr>
<tr class="odd">
<td>Creare e visualizzare riunioni in Teams</td>
<td><p>Possibilità di creare riunioni interne ed esterne tramite Outlook componente aggiuntivo.</p>
<p>La funzionalità Dial in e Dialout PSTN è disponibile con le licenze per i servizi di audioconferenza.</p>
<p>Teams l'accesso al calendario richiede Exchange 2016 CU3+ in locale distribuito con Exchange distribuzione ibrida stabilita: <a href="/exchange/hybrid-deployment/deploy-hybrid">Creare una distribuzione ibrida con la procedura guidata Configurazione ibrida.</a> </p>

Oltre a Exchange configurazione ibrida, stabilire Exchange autenticazione OAuth: [Configurare l'autenticazione OAuth tra Exchange e organizzazioni Exchange Online](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help). 

</p></td>
</tr>
<tr class="even">
<td>Funzionalità di chiamata<br />
VoIP/PSTN in Teams</td>
<td><p>VoIP internamente ed esternamente al tenant è disponibile.</p>
<p>I servizi PSTN possono essere configurati tramite Telefono Microsoft System, oltre all'aggiunta di un piano per chiamate Microsoft o di routing diretto.</p></td>
</tr>
<tr class="odd">
<td>Collaborazione Teams e canali in Teams</td>
<td><p>Per un'esperienza completa, incluse le caratteristiche di conformità, è necessario assegnare all'utente una licenza di SharePoint Online.</p>
<p>La migrazione dei siti SharePoint locali esistenti non è necessaria.</p></td>
</tr>
<tr class="even">
<td>OneDrive for Business (condivisione file P2P)</td>
<td>OneDrive for Business richiede che a un utente sia assegnata una licenza di SharePoint Online. Senza questa licenza non sarà possibile condividere file peer-to-peer.</td>
</tr>
<tr class="odd">
<td>Piattaforma delle applicazioni</td>
<td>Gli utenti potranno usare le app designate disponibili in base ai criteri aziendali.<br />
Altre informazioni sono disponibili qui: <a href="/microsoftteams/admin-settings">Impostazioni di amministrazione per le app in Teams</a></td>
</tr>
<tr class="even">
<td>Caratteristiche di sicurezza e conformità</td>
<td><ul>
<li><p>Sono disponibili criteri di conservazione.</p></li>
<li><p>Sono supportati eDiscovery e un blocco legale per la conformità nei messaggi del canale.</p></li>
<li><p>Sono disponibili criteri di prevenzione della perdita dei dati.</p></li>
</ul>
<p>Set di funzionalità completo disponibile con Exchange Online; Exchange locale supporta la maggior parte di queste caratteristiche. Per un elenco completo, vedi <a href="/MicrosoftTeams/exchange-teams-interact">Come interagiscono Exchange e Teams</a>.</p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a>Passaggi di abilitazione per le organizzazioni senza Skype for Business o Lync Server

1.  Ecco i prerequisiti descritti nella sezione Iniziare qui sopra

2.  Passare il tenant alla modalità solo Teams (solo per i tenant esistenti): [impostazione delle impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md).

3.  Configurare il tenant in base ai criteri aziendali e aziendali: [Gestire le impostazioni di Microsoft Teams per l'organizzazione](enable-features-office-365.md).

4.  Distribuire il client Teams agli utenti: [Ottenere i client per Teams](get-clients.md)

5.  Guidare il programma di adozione  
    [Adottare Microsoft Teams](adopt-microsoft-teams-landing-page.md)
    
    [Elenco di controllo per l'adozione rapida di Microsoft Teams](teams-adoption-quick-start-checklist.md)

6.  Iniziare a pianificare lo spostamento di altri carichi di lavoro in Microsoft 365 o Office 365

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a>Organizzazioni **<span class="underline">con</span>** Skype for Business o Lync Server

Questo punto di partenza presuppone che l'organizzazione utilizzi Skype for Business server 2019 o 2015+ o Lync 2013+ in locale. Sono già disponibili indicazioni dettagliate per le organizzazioni che eseguiranno la migrazione da server locali a Teams e dovrebbero essere seguite per questi scenari. Queste linee guida sono specifiche per lo scenario che Teams è la prima applicazione che si utilizza in Microsoft 365 o Office 365. La tabella seguente descrive in dettaglio le funzionalità di configurazione di alto livello e degli utenti finali per Teams per i servizi di base.

<table>
<thead>
<tr class="header">
<th>Elemento</th>
<th>Note</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Configurazione Teams tenant</td>
<td>Modalità Isole.</td>
</tr>
<tr class="even">
<td>Chat/ Comunicazione esterna in Teams</td>
<td>All'interno del solo tenant, la comunicazione esterna (federazione) avviene tramite la distribuzione di Skype for Business o Lync Server.</td>
</tr>
<tr class="odd">
<td>Creare e visualizzare riunioni in Teams</td>
<td><p>Possibilità di creare riunioni interne ed esterne tramite Outlook componente aggiuntivo.</p>
<p>La funzionalità Dial in e Dialout PSTN è disponibile con le licenze per i servizi di audioconferenza.</p>
<p>Teams l'accesso al calendario richiede Exchange 2016 CU3+ in locale distribuito con Exchange configurazione ibrida:<br />
<a href="/exchange/hybrid-deployment/deploy-hybrid">Creare una distribuzione ibrida con la Configurazione ibrida guidata.</a></p>
<p>L'amministratore può controllare il componente aggiuntivo Skype for Business Outlook tramite l'attributo PreferredMeetingProviderForIslandsMode del criterio di riunione Teams:<a href="/powershell/module/skype/set-csteamsmeetingpolicy"> set-csteamsmeetingpolicy</a>.</p> 
</td>
</tr>
<tr class="even">
<td>Funzionalità di chiamata<br />
VoIP/PSTN in Teams</td>
<td><p>VoIP internamente al tenant è disponibile.</p>
<p>I servizi PSTN o Piano per chiamate non sono disponibili finché l'utente non viene spostato nell'esperienza Solo Teams.</p></td>
</tr>
<tr class="odd">
<td>Collaborazione Teams e canali in Teams</td>
<td><p>Per un'esperienza completa, incluse le caratteristiche di conformità, è necessario assegnare all'utente una licenza di SharePoint Online.</p>
<p>La migrazione dei siti SharePoint locali esistenti non è necessaria.</p></td>
</tr>
<tr class="even">
<td>OneDrive for Business (condivisione file P2P)</td>
<td>OneDrive for Business richiede che a un utente sia assegnata una licenza di SharePoint Online. Senza questa licenza non sarà possibile condividere file per peer.</td>
</tr>
<tr class="odd">
<td>Piattaforma delle applicazioni</td>
<td>Gli utenti potranno usare le app designate disponibili in base ai criteri aziendali.<br />
Altre informazioni sono disponibili qui: <a href="/microsoftteams/admin-settings">Impostazioni di amministrazione per le app in Teams</a></td>
</tr>
<tr class="even">
<td>Caratteristiche di sicurezza e conformità</td>
<td><ul>
<li><p>Sono disponibili criteri di conservazione.</p></li>
<li><p>Sono supportati eDiscovery e un blocco legale per la conformità nei messaggi del canale.</p></li>
<li><p>Sono disponibili criteri di prevenzione della perdita dei dati.</p></li>
</ul>
<p>Set di funzionalità completo disponibile con Exchange Online; Exchange locale supporta la maggior parte di queste caratteristiche. Per un elenco completo, vedi <a href="/MicrosoftTeams/exchange-teams-interact">Come interagiscono Exchange e Teams.</a></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a>Passaggi di abilitazione per le organizzazioni con Skype for Business Server  

1.  Ecco i prerequisiti descritti nella sezione Iniziare qui precedente.

2.  Passare il tenant alla modalità Isole (per i tenant di cui è stato eseguito il provisioning dopo l'1/9/2019, contatta il supporto tecnico per apportare questa modifica)  
    [Impostazione delle impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md)

3.  Configurare il tenant in base ai criteri aziendali e aziendali  
    [Gestire le impostazioni di Microsoft Teams per l'organizzazione](enable-features-office-365.md)

4.  Distribuire il client Teams  
    [Ottenere client per Teams](get-clients.md)

5.   Guidare il programma di adozione  
    [Adottare Microsoft Teams](adopt-microsoft-teams-landing-page.md)<br/>
    [Elenco di controllo per l'adozione rapida di Microsoft Teams](teams-adoption-quick-start-checklist.md)

6.  Iniziare a pianificare lo spostamento di altri carichi di lavoro in Microsoft 365 o Office 365

7.  Stabilire Skype for Business ibrida e seguire i percorsi di aggiornamento consigliati per i server Skype for Business e Lync  
    [Eseguire l'aggiornamento da Skype for Business locale a Teams](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a>Estratto conto di chiusura

Microsoft Teams può consentire all'organizzazione di riunire tutti i dipendenti, gli information worker e gli operatori in prima linea in un'unica piattaforma. Puoi [iniziare](https://products.office.com/microsoft-teams/group-chat-software) oggi stesso. Puoi rimanere in contatto con tutti i nostri ultimi annunci e gli aggiornamenti mensili dei prodotti [qui](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog).

Inoltre, dato che le aziende in tutto il mondo gestiscono l'attuale situazione di SCREENSHOT-19, abbiamo creato una serie di contenuti che ti aiuteranno a utilizzare Teams per il massimo impatto nella tua organizzazione.

  - Il nostro [impegno per i clienti durante la fase DELL-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)

  - [2 settimane dopo: quello che abbiamo imparato sul lavoro remoto](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [Organizzare riunioni ed eventi online](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [Aiutare le piccole e medie imprese a lavorare in remoto con Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [Trasformazione digitale degli eventi live: osservazioni di Bob Bejan in prima linea](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [I principali 9 modi in cui Microsoft IT sta abilitando il lavoro remoto per i suoi dipendenti](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [Lavora in remoto, mantieni la sicurezza: suggerimenti per i ciotoli](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [Aiutare insegnanti e studenti a passare all'apprendimento remoto](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [Rimanere produttivi mentre si lavora in remoto con Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a>Informazioni di riferimento per i servizi di supporto tecnico

Teams si basa su Exchange Online, SharePoint Online, OneDrive for Business e Gruppi di Microsoft 365 per offrire agli utenti una Microsoft 365 completamente integrata o Office 365 esperienza. Come indicato in precedenza, Teams funzionerà senza la distribuzione completa di questi servizi, con funzionalità limitate. Altre informazioni su Teams e sui prerequisiti sono disponibili qui: [Benvenuto in Teams](teams-overview.md).

Per informazioni specifiche su ognuno dei servizi sopra elencati, seguire i collegamenti seguenti:

  - Exchange Online viene usato per le caratteristiche di calendario e l'archiviazione dei messaggi peer-to-peer in Teams. Per altre informazioni, leggi [Come interagiscono Exchange e Teams](exchange-teams-interact.md)

> [!IMPORTANT]
> Per Teams interoperabilità con Exchange locale, è necessario configurare il nuovo protocollo di autenticazione OAuth Exchange, come descritto in [Configurare l'autenticazione OAuth tra organizzazioni Exchange e Exchange Online](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).

  - SharePoint viene usato per la condivisione di file nei canali, mentre /OneDrive for Business viene usato per la condivisione di file in 1:1 o chat di gruppo. Per altre informazioni, vedere [Come SharePoint Online e OneDrive for Business interagire con Microsoft Teams](sharepoint-onedrive-interact.md).

  - [Gruppi di Microsoft 365](office-365-groups.md) vengono utilizzati per la creazione/gestione di team e canali.


## <a name="related-topics"></a>Argomenti correlati

[Poster di soluzioni di telefonia e architettura IT di Microsoft Teams](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[Pianificare la connettività ibrida tra Skype for Business Server e Office 365](/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[Supportare gli operatori remoti che usano Teams](support-remote-work-with-teams.md)

[Lavorare in remoto con Microsoft 365](https://aka.ms/remote-work)
