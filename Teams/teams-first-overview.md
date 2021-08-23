---
title: Implementare Microsoft Teams First
author: LaszloSomi
ms.author: lsomi
manager: swerth
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: lsomi
localization_priority: Normal
search.appverid: MET150
description: Usare queste indicazioni per implementare Microsoft Teams come prima Microsoft 365 o Office 365 carico di lavoro.
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: b52bbef87b08fd541a444e5613aed17032739f67
ms.sourcegitcommit: 2e1d97a3181fe12be43a0641039dca6077863f44
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/18/2021
ms.locfileid: "58380440"
---
# <a name="roll-out-microsoft-teams-first"></a>Implementare Microsoft Teams First

Microsoft Teams può aiutare i dipendenti a rimanere in contatto e collaborare tra loro, soprattutto nell'attuale periodo senza precedenti in cui il lavoro remoto è una realtà dei dipendenti di tutto il mondo. La possibilità di chattare, fare riunioni video e collaborare Office documenti all'interno Teams può aiutare le aziende a rimanere produttive. Sia che si sia una piccola azienda, un'organizzazione no profit o un'organizzazione di grandi dimensioni, è possibile iniziare a usare Teams come primo carico di lavoro all'interno di Microsoft 365 o Office 365 prima di distribuire qualsiasi altro app Office o servizio.

Questo articolo descrive in dettaglio le considerazioni da prendere con l'approccio "Teams First".

> [!IMPORTANT]
> Anche Teams essere il primo carico di lavoro distribuito nel cloud dell'organizzazione, la distribuzione Teams dovrebbe far parte della strategia di distribuzione cloud complessiva.

Se sono già stati implementazioni di altri servizi Microsoft 365 o Office 365 e Teams è il carico di lavoro successivo da implementare (invece del [primo),](./deploy-overview.md)iniziare con Come implementare Teams .

## <a name="start-here"></a>Iniziare da qui

Per iniziare a usare il Teams prima distribuzione, è necessario soddisfare almeno alcuni prerequisiti. L'elenco seguente mostra ciò che è necessario avere in essere per l'organizzazione prima Teams può essere abilitato:

1.  Un'Microsoft 365 o Office 365 configurata con il nome di dominio

2.  Azure Active Directory connettività (connessione AAD) o una soluzione di sincronizzazione delle identità cloud simile, con tutti gli attributi obbligatori sincronizzati con il tenant  
    Per comprendere gli attributi sincronizzati con la sincronizzazione AAD, vedere Sincronizzazione Connessione [Azure AD: Attributi sincronizzati con Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)

3.  Licenze utente appropriate assegnate per Teams  
    Per informazioni sulle Teams licenze, leggere Microsoft Teams [Descrizione del servizio.](/office365/servicedescriptions/teams-service-description)

4.  Rete dell'organizzazione preparata per Teams  
    Per informazioni sulla preparazione della rete, vedere Preparare la rete [dell'organizzazione](prepare-network.md)per Teams .

5.  Consentire l'accesso di rete Exchange, SharePoint e OneDrive for Business in Microsoft 365 o Office 365: URL Office 365 e intervalli di indirizzi [IP.](/office365/enterprise/urls-and-ip-address-ranges)

> [!NOTE]
> Il provisioning dei tenant creati dopo il 1° settembre 2019 viene eseguito in modalità Teams solo per i tenant.
> 
> [!IMPORTANT]
> Se è stato distribuito Skype for Business Server e il provisioning del tenant è stato eseguito dopo l'1 settembre 2019, contattare il supporto per abilitare le funzionalità di coesistenza per Teams. Assicurarsi che il criterio di aggiornamento a livello di organizzazione sia impostato su "Modalità <span class="underline">isola"</span> prima di assegnare le licenze Teams a un utente.

## <a name="migration-starting-points"></a>Punti di partenza della migrazione

Il percorso verso Microsoft 365 o Office 365 e le funzionalità disponibili in Teams a seconda del punto di partenza e dell'esistenza di Skype for Business locale o Lync Server. Le sezioni seguenti illustrano in dettaglio le funzionalità di base e le opzioni di configurazione oltre ai prerequisiti descritti sopra. Gli scenari del punto di partenza sono stati suddivisi negli argomenti seguenti:

**Configurazione Teams tenant:** le modalità tenant e utente vengono usate per controllare il comportamento del destinatario. Queste impostazioni possono essere assegnate a livello di tenant o di utente in un'organizzazione. Per altre informazioni, vedere [Coesistenza con Skype for Business](coexistence-chat-calls-presence.md).

**Comunicazione chat/esterna in Teams:** i servizi chat fanno riferimento a conversazioni peer-to-peer o chat di gruppo all'interno e all'organizzazione o esternamente all'organizzazione. La comunicazione esterna è detta anche federazione in Skype for Business.

Creare e visualizzare riunioni **in Teams:** un utente può sempre creare riunioni online tramite il componente aggiuntivo Outlook Teams e l'accesso pstn è disponibile in tutti gli scenari dopo che l'utente ha una licenza. Teams e Skype for Business le informazioni del calendario nella cassetta postale Exchange'utente. Il server Exchange locale deve essere Exchange Server 2016 CU3 o versioni successive perché il client di Teams sia in grado di interagire con la cassetta postale dell'utente. Senza Exchange cassetta postale, l'icona Calendario in Teams non verrà visualizzata e l'utente non sarà in grado di visualizzare, creare o modificare riunioni nel client Teams.

**Funzionalità di chiamata VoIP/PSTN in Teams:** le chiamate possono essere Voice over IP (VoIP) o PSTN (Public Switched Telephone Network). La connettività VoIP avviene in Teams client, mentre la connettività PSTN avviene quando un utente compone un numero di telefono esterno.  

Teams due tipi di connettività PSTN. Piano per chiamate Microsoft, quando Microsoft fornisce un'infrastruttura di telefonia, incluso il numero di telefono di un utente, o la configurazione del routing diretto, in cui il cliente fornisce la connettività di telefonia tramite un session border controller (SBC) per l'utente Teams.  
Per altre informazioni, vedere Quale piano di chiamata è più giusto [per te?](calling-plan-landing-page.md) e Sistema telefonico [Routing diretto](direct-routing-landing-page.md).

**Teams e canali in Teams:** in Teams, i team sono gruppi di persone riunite per lavoro, progetti o interessi comuni. Teams sono di canali. Ogni canale è basato su un argomento, ad esempio "Eventi del team", un nome di reparto o solo per divertimento. I canali sono la posizione in cui si tengono riunioni, si hanno conversazioni e si lavora insieme ai file. Durante la collaborazione

**OneDrive for Business (condivisione di file P2P) in Teams:** all'esterno di Teams e canali, gli utenti di Teams possono condividere file peer-to-peer usando OneDrive per le aziende o altri programmi di file di condivisione P2P come File Citrix, DropBox, Box e Google Drive. Per OneDrive per le aziende un utente deve avere SharePoint licenza online.

**Piattaforma applicativa:** le app forniscono strumenti avanzati per l'organizzazione per ottenere il maggior numero di Teams. Queste app combinano le funzionalità di schede, estensioni di messaggistica, connettori e bot forniti da Microsoft, creati da terze parti o da sviluppatori dell'organizzazione.

Caratteristiche di sicurezza e **conformità:** Teams offre un'ampia gamma di informazioni utili per le aree di conformità, inclusi i criteri di conservazione, la prevenzione della perdita dei dati (DLP), eDiscovery e il blocco legale per canali, chat e file, ricerca nel log di controllo. Per altre informazioni, vedere [Sicurezza e conformità in Microsoft Teams](security-compliance-overview.md).  

> [!NOTE]
> Le funzionalità avanzate di eDiscovery richiedono la licenza E5.

[Confrontare le opzioni di licenza](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).

Leggere [Come Exchange e Microsoft Teams informazioni](exchange-teams-interact.md) sulle caratteristiche di conformità disponibili nello scenario.

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a>Organizzazioni senza **<span class="underline">Skype for Business</span>** o Lync Server

Questo punto di partenza presuppone che l'organizzazione non usa attualmente Skype for Business o Lync Server e Teams sarà la prima applicazione in Microsoft 365 o Office 365. La tabella seguente contiene informazioni dettagliate sulla configurazione di alto livello e sulle funzionalità per gli utenti finali Teams per i servizi di base.

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
<td>Teams Solo modalità, tutte le funzionalità di chat e chiamate sono Teams solo.</td>
</tr>
<tr class="even">
<td>Chat/Comunicazioni esterne in Teams</td>
<td><p>Le comunicazioni interne (Microsoft 365 o Office 365) e la chat esterna possono essere Teams.</p>
<p><em>Nota: le voci DNS devono essere configurate per l'accesso esterno. Skype for Business I record DNS sono necessari anche se non si hanno Skype for Business locali o in Microsoft 365 o Office 365, per consentire la federazione con lync e gli ambienti Skype for Business:<br />
<a href="/office365/enterprise/external-domain-name-system-records">Record domain name system esterni</a></em></p></td>
</tr>
<tr class="odd">
<td>Creare e visualizzare riunioni in Teams</td>
<td><p>Possibilità di creare riunioni interne ed esterne tramite Outlook componente aggiuntivo.</p>
<p>La funzionalità Chiamata in ingresso e uscita PSTN è disponibile con le licenze di audioconferenza.</p>
<p>Teams l'accesso al calendario richiede Exchange 2016 CU3+ in locale distribuito con una distribuzione ibrida di Exchange: Creare una distribuzione ibrida con la procedura guidata Configurazione <a href="/exchange/hybrid-deployment/deploy-hybrid">ibrida.</a> </p>

Oltre alla configurazione Exchange ibrida, stabilire Exchange autenticazione OAuth: Configurare l'autenticazione [OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)tra Exchange e Exchange Online organizzazioni . 

</p></td>
</tr>
<tr class="even">
<td>Funzionalità di chiamata<br />
VoIP/PSTN in Teams</td>
<td><p>VoIP internamente ed esternamente al tenant è disponibile.</p>
<p>I servizi PSTN possono essere configurati tramite Telefono Microsoft sistema, oltre ad aggiungere un piano per chiamate Microsoft o un routing diretto.</p></td>
</tr>
<tr class="odd">
<td>Teams e canali in Teams</td>
<td><p>Per un'esperienza completa, incluse le funzionalità di conformità, è SharePoint all'utente deve essere assegnata una licenza online.</p>
<p>Non è necessaria la migrazione di siti SharePoint locali esistenti.</p></td>
</tr>
<tr class="even">
<td>OneDrive for Business (condivisione file P2P)</td>
<td>OneDrive for Business un utente deve avere una licenza SharePoint Online. Senza questa licenza, la condivisione di file peer-to-peer non sarà possibile.</td>
</tr>
<tr class="odd">
<td>Piattaforma dell'applicazione</td>
<td>Gli utenti potranno usare le app designate per loro in base ai criteri aziendali.<br />
Altre informazioni qui: <a href="/microsoftteams/admin-settings">Impostazioni di amministratore per le app in Teams</a></td>
</tr>
<tr class="even">
<td>Caratteristiche di sicurezza e conformità</td>
<td><ul>
<li><p>Sono disponibili criteri di conservazione.</p></li>
<li><p>Sono supportati eDiscovery e blocco legale per la conformità ai messaggi del canale.</p></li>
<li><p>Sono disponibili i criteri di prevenzione della perdita dei dati.Data Loss Prevention policies (DLP) are available.</p></li>
</ul>
<p>Set di funzionalità completo disponibile con Exchange Online; Exchange locale supporta la maggior parte di queste caratteristiche. Per un elenco completo, vedere Come Exchange <a href="/MicrosoftTeams/exchange-teams-interact">e Teams interagire.</a></p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a>Passaggi di abilitazione per le organizzazioni senza Skype for Business o Lync Server

1.  Ecco i prerequisiti descritti in dettaglio nella sezione Iniziare qui riportata sopra

2.  Impostare la modalità solo Teams tenant (solo per i tenant esistenti): impostazione delle impostazioni di [coesistenza e aggiornamento.](setting-your-coexistence-and-upgrade-settings.md)

3.  Configurare il tenant in base ai criteri aziendali/aziendali dell'azienda: Gestire le Microsoft Teams [per l'organizzazione.](enable-features-office-365.md)

4.  Distribuire il Teams client agli utenti: [Ottenere i client per Teams](get-clients.md)

5.  Guida il tuo programma di adozione  
    [Adottare Microsoft Teams](adopt-microsoft-teams-landing-page.md)
    
    [Microsoft Teams elenco di controllo introduttivo sull'adozione](teams-adoption-quick-start-checklist.md)

6.  Iniziare a pianificare lo spostamento di altri carichi di lavoro Microsoft 365 o Office 365

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a>Organizzazioni con **<span class="underline">Skype for Business</span>** o Lync Server

Questo punto di partenza presuppone che l'organizzazione Skype for Business server 2019 o 2015+ o Lync 2013+ locale. Sono già disponibili indicazioni approfondite per le organizzazioni che esere esere in grado di eseguire la migrazione da server locali a Teams e devono essere seguite per questi scenari. Queste indicazioni sono specifiche dello scenario che Teams è la prima applicazione che si usa in Microsoft 365 o Office 365. La tabella seguente contiene informazioni dettagliate sulla configurazione di alto livello e sulle funzionalità per gli utenti finali Teams per i servizi di base.

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
<td>Chat/Comunicazioni esterne in Teams</td>
<td>Interno solo all'interno del proprio tenant, la comunicazione esterna (federazione) avviene tramite la distribuzione Skype for Business o Lync Server.</td>
</tr>
<tr class="odd">
<td>Creare e visualizzare riunioni in Teams</td>
<td><p>Possibilità di creare riunioni interne ed esterne tramite Outlook componente aggiuntivo.</p>
<p>La funzionalità Chiamata in ingresso e uscita PSTN è disponibile con le licenze di audioconferenza.</p>
<p>Teams l'accesso al calendario Exchange 2016 CU3+ locale distribuito con Exchange ibrido:<br />
<a href="/exchange/hybrid-deployment/deploy-hybrid">Creare una distribuzione ibrida con la procedura guidata Configurazione ibrida.</a></p>
<p>L'amministratore può controllare Skype for Business Outlook componente aggiuntivo tramite l'attributo PreferredMeetingProviderForIslandsMode del criterio di riunione Teams:<a href="/powershell/module/skype/set-csteamsmeetingpolicy"> set-csteamsmeetingpolicy</a>.</p> 
</td>
</tr>
<tr class="even">
<td>Funzionalità di chiamata<br />
VoIP/PSTN in Teams</td>
<td><p>VoIP internamente al tenant è disponibile.</p>
<p>I servizi PSTN o Piano per chiamate non sono disponibili finché l'utente non viene spostato in Teams solo utenti.</p></td>
</tr>
<tr class="odd">
<td>Teams e canali in Teams</td>
<td><p>Per un'esperienza completa, incluse le caratteristiche di conformità, è SharePoint all'utente deve essere assegnata una licenza online.</p>
<p>Non è necessaria la migrazione di siti SharePoint locali esistenti.</p></td>
</tr>
<tr class="even">
<td>OneDrive for Business (condivisione file P2P)</td>
<td>OneDrive for Business un utente deve avere una licenza SharePoint online. Senza questa licenza non sarà possibile condividere file per peer.</td>
</tr>
<tr class="odd">
<td>Piattaforma dell'applicazione</td>
<td>Gli utenti potranno usare le app designate per loro in base ai criteri aziendali.<br />
Altre informazioni qui: <a href="/microsoftteams/admin-settings">Impostazioni di amministratore per le app in Teams</a></td>
</tr>
<tr class="even">
<td>Caratteristiche di sicurezza e conformità</td>
<td><ul>
<li><p>Sono disponibili criteri di conservazione.</p></li>
<li><p>Sono supportati eDiscovery e blocco legale per la conformità ai messaggi del canale.</p></li>
<li><p>Sono disponibili i criteri di prevenzione della perdita dei dati.Data Loss Prevention policies (DLP) are available.</p></li>
</ul>
<p>Set di funzionalità completo disponibile con Exchange Online; Exchange locale supporta la maggior parte di queste caratteristiche. Per un elenco completo, vedere Come Exchange <a href="/MicrosoftTeams/exchange-teams-interact">e Teams interagire.</a></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a>Passaggi di abilitazione per le organizzazioni con Skype for Business Server  

1.  Ecco i prerequisiti descritti in dettaglio nella sezione Iniziare qui sopra.

2.  Passare alla modalità Isole (per i tenant di cui è stato eseguito il provisioning DOPO l'1/9/2019, contattare il supporto tecnico per apportare questa modifica)  
    [Impostazione delle impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md)

3.  Configurare il tenant in base ai criteri aziendali/aziendali dell'azienda  
    [Gestire le impostazioni di Microsoft Teams per l'organizzazione](enable-features-office-365.md)

4.  Distribuire il client Teams client  
    [Ottenere client per Teams](get-clients.md)

5.   Guida il tuo programma di adozione  
    [Adottare Microsoft Teams](adopt-microsoft-teams-landing-page.md)<br/>
    [Microsoft Teams elenco di controllo introduttivo sull'adozione](teams-adoption-quick-start-checklist.md)

6.  Iniziare a pianificare lo spostamento di altri carichi di lavoro Microsoft 365 o Office 365

7.  Stabilire Skype for Business ibrida e seguire i percorsi di aggiornamento consigliati per i Skype for Business e i server Lync  
    [Eseguire l'aggiornamento da Skype for Business locale a Teams](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a>Istruzione di chiusura

Microsoft Teams può essere un'opzione che consente all'organizzazione di riunire tutti i dipendenti, gli information worker e i frontline worker su un'unica piattaforma. È possibile [iniziare oggi](https://products.office.com/microsoft-teams/group-chat-software) stesso. È possibile rimanere in contatto con tutti gli ultimi annunci e gli aggiornamenti mensili dei prodotti [qui.](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)

Inoltre, poiché le aziende di tutto il mondo gestiscono l'attuale situazione di COVID-19, abbiamo creato una serie di contenuti che ti aiuteranno a usare Teams per il massimo impatto nell'organizzazione.

  - Il [nostro impegno per i clienti durante COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)

  - [2 settimane in: ciò che abbiamo imparato sul lavoro remoto](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [Distribuzione di riunioni ed eventi online](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [Aiutare le piccole e medie imprese a lavorare in remoto con Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [Trasformazione digitale degli eventi live: le osservazioni di Bob Bejan dalla prima linea](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [I principali 9 modi in cui Microsoft IT sta abilitando il lavoro remoto per i suoi dipendenti](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [Lavorare in remoto, rimanere al sicuro: suggerimenti per i CISO](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [Aiutare insegnanti e studenti a passare all'apprendimento remoto](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [Rimanere produttivi mentre si lavora in remoto con Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a>Informazioni di riferimento su Servizi di supporto

Teams si basa su Exchange Online, SharePoint Online, OneDrive for Business e gruppi di Microsoft 365 per offrire agli utenti un'esperienza Microsoft 365 o Office 365 completamente integrata. Come indicato in precedenza, Teams la distribuzione completa di questi servizi, con funzionalità limitate. Per altre informazioni sui Teams e sui prerequisiti, vedere: [Benvenuto in Teams.](teams-overview.md)

Per informazioni specifiche su ognuno dei servizi elencati sopra, seguire i collegamenti seguenti:

  - Exchange Online viene usato per le funzionalità di calendario e per l'archiviazione di messaggi peer-to-peer in Teams. Per altre informazioni, vedere [Come Exchange e Teams interagire](exchange-teams-interact.md)

> [!IMPORTANT]
> Per Teams'interoperabilità con Exchange locale, è necessario configurare il nuovo protocollo di autenticazione OAuth di Exchange come descritto in Configurare l'autenticazione OAuth tra organizzazioni Exchange e [Exchange Online.](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

  - SharePoint viene usato per la condivisione di file nei canali, mentre /OneDrive for Business viene usato per la condivisione di file in 1:1 o chat di gruppo. Per altre informazioni, vedere [Come SharePoint Online e OneDrive for Business interagire con Microsoft Teams](sharepoint-onedrive-interact.md).

  - [Microsoft 365 gruppi vengono](office-365-groups.md) usati per la creazione/gestione di team e canali.


## <a name="related-topics"></a>Argomenti correlati

[Poster di soluzioni di telefonia e architettura IT di Microsoft Teams](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[Pianificare la connettività ibrida tra Skype for Business Server e Office 365](/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[Supportare i lavoratori remoti con Teams](support-remote-work-with-teams.md)

[Lavorare in remoto con Microsoft 365](https://aka.ms/remote-work)
