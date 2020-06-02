---
title: Distribuire prima Microsoft Teams
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
description: Usare queste linee guida per implementare Microsoft teams come primo carico di lavoro di Office 365.
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 647f6879f7892c1a65599832e48deb67e183fae0
ms.sourcegitcommit: bdafa1f4146e615d325e27a50352f10c0d51ef1a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2020
ms.locfileid: "44472347"
---
# <a name="roll-out-microsoft-teams-first"></a>Distribuire prima Microsoft Teams

Microsoft teams può aiutare i dipendenti a rimanere connessi e collaborare tra loro, in particolare nell'attuale tempo senza precedenti in cui il lavoro remoto è una realtà dei dipendenti in tutto il mondo. La possibilità di chattare, eseguire riunioni video e collaborare ai documenti di Office all'interno di teams può aiutare le aziende a rimanere produttivi. Che tu sia una piccola impresa, un'organizzazione no profit o di grandi dimensioni, puoi iniziare a usare teams come primo carico di lavoro all'interno di Office 365 Suite prima di distribuire qualsiasi altra app o servizio di Office.

In questo articolo vengono fornite informazioni dettagliate sulle considerazioni che è necessario apportare con l'approccio "Teams First".

> [!IMPORTANT]
> Mentre i team possono essere il primo carico di lavoro distribuito nel cloud dell'organizzazione, la distribuzione dei team deve far parte della strategia globale di distribuzione del cloud.

Se sono già stati implementati altri servizi di Office 365 e teams è il carico di lavoro successivo da implementare (invece del primo), iniziare con la [modalità di implementazione dei team](How-to-roll-out-teams.md).

## <a name="start-here"></a>Iniziare da qui

Per iniziare a usare la prima distribuzione di teams, è necessario soddisfare almeno alcuni requisiti preliminari. L'elenco seguente mostra le informazioni che è necessario avere sul posto per l'organizzazione prima che i team possano essere abilitati:

1.  Un'organizzazione di Office 365 configurata con il nome di dominio

2.  Azure Active Directory Connectivity (AAD Connect) o una simile soluzione di sincronizzazione delle identità cloud, con tutti gli attributi necessari sincronizzati con il tenant  
    Per comprendere gli attributi sincronizzati con la sincronizzazione AAD, leggere [Azure ad Connect Sync: attributi sincronizzati con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)

3.  Licenze utente appropriate assegnate per i team  
    Per informazioni sulle licenze di teams, leggere la [Descrizione del servizio Microsoft teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).

4.  Rete dell'organizzazione predisposta per i team  
    Per informazioni sulla preparazione della rete, leggere [preparare la rete dell'organizzazione per i team](prepare-network.md).

5.  Consentire l'accesso di rete a Exchange, SharePoint e OneDrive for business in Office 365: [URL e intervalli di indirizzi IP di office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).

> [!NOTE]
> I tenant creati dopo il 1 ° settembre 2019 vengono provisionati in modalità solo teams.
> 
> [!IMPORTANT]
> Se si è distribuito Skype for Business Server e il tenant è stato effettuato il provisioning dopo il 2019 settembre, contattare il supporto tecnico per abilitare le funzionalità di coesistenza per i team. Verificare che il criterio "organizzazione Wide Upgrade policy" sia impostato su "modalità Isola" <span class="underline">prima</span> di assegnare le licenze per i team a un utente.

## <a name="migration-starting-points"></a>Punti di partenza della migrazione

Il viaggio in Office 365 e le caratteristiche disponibili in teams a seconda del punto di partenza e dell'esistenza dei locali Skype for business o Lync Server. Le sezioni seguenti illustrano in dettaglio le funzionalità di base e le opzioni di configurazione oltre ai prerequisiti precedenti. Sono stati suddivisi gli scenari del punto di partenza per gli argomenti seguenti:

**Configurazione del tenant teams**: le modalità tenant e User vengono usate per controllare il comportamento del destinatario. Queste impostazioni possono essere assegnate a livello di tenant o a livello di utente in un'organizzazione. Per altre informazioni, leggi [la coesistenza con Skype for business](coexistence-chat-calls-presence.md).

**Chat/comunicazioni esterne in teams**: i servizi di chat fanno riferimento alle conversazioni peer-to-peer o di chat di gruppo all'interno e all'organizzazione o all'esterno dell'organizzazione. La comunicazione esterna viene definita anche federazione in Skype for business.

**Creare e visualizzare riunioni in teams**: un utente può sempre creare riunioni online tramite il componente aggiuntivo di Outlook teams e il dial-in PSTN è disponibile in tutti gli scenari una volta che l'utente ha una licenza. Teams e Skype for business memorizzano le informazioni del calendario nella cassetta postale di Exchange dell'utente. In locale Exchange Server deve essere Exchange Server 2016 CU3 o versioni successive per consentire al client teams di interagire con la cassetta postale dell'utente. Senza accesso alle cassette postali di Exchange l'icona del calendario in teams non verrà visualizzata e l'utente non sarà in grado di visualizzare, creare o modificare riunioni nel client teams.

**Chiamata di funzionalità VoIP/PSTN in teams**: la chiamata può essere VoIP (Voice over IP) o PSTN (Public Switched Telephone Network). La connettività VoIP avviene a livello nativo tra i client dei team, mentre la connettività PSTN si verifica quando un utente compone un numero di telefono esterno.  

I team supportano due tipi di connettività PSTN. Piano di chiamate Microsoft, quando Microsoft fornisce l'infrastruttura per la telefonia, incluso il numero di telefono di un utente o la configurazione del routing diretto, in cui il cliente fornisce la connettività telefonica su un SBC (Session Border Controller) per l'utente di teams.  
Per altre informazioni, leggere [quale piano per le chiamate è giusto per l'utente?](calling-plan-landing-page.md) e [sistema telefonico Direct routing](direct-routing-landing-page.md).

**Collaborazione di team e canali in**teams: in teams, teams sono gruppi di persone riunite per lavoro, progetti o interessi comuni. I team sono costituiti da canali. Ogni canale è costruito attorno a un argomento, ad esempio "eventi del team", un nome di reparto o solo per divertimento. I canali sono il luogo in cui si organizzano riunioni, si hanno conversazioni e si lavora insieme ai file. Durante la collaborazione

**OneDrive for business (P2P file sharing) in teams: al**di fuori di team e canali, gli utenti del team possono condividere file peer-to-peer usando OneDrive for business o altri programmi di condivisione di file P2P, come file Citrix, Dropbox, box e Google Drive. Per OneDrive for business un utente deve avere la licenza di SharePoint Online assegnata.

**Piattaforma applicativa**: le app contengono strumenti fuori sede per l'organizzazione per ottenere un numero maggiore di team. Queste app combinano la funzionalità di schede, estensioni di messaggistica, connettori e bot forniti da Microsoft, creati da terze parti o da sviluppatori dell'organizzazione.

**Caratteristiche di sicurezza e conformità:** Teams offre una vasta gamma di informazioni per aiutarti con le aree di conformità, inclusi i criteri di conservazione, la protezione dalla perdita dei dati (DLP), eDiscovery e il blocco legale per canali, chat e file, ricerca nel log di controllo. Per altre informazioni, leggere [sicurezza e conformità in Microsoft teams](security-compliance-overview.md).  

> [!NOTE]
> Advance eDiscovery caratteristiche richiedono licenze E5.

[Confrontare le opzioni di licenza](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).

Leggere [come interagiscono Exchange e Microsoft teams](exchange-teams-interact.md) per scoprire quali funzionalità di conformità sono disponibili nello scenario.

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a>Organizzazioni **<span class="underline">senza</span>** Skype for business o Lync Server

Questo punto di partenza presuppone che l'organizzazione non utilizzi Skype for business o Lync Server attualmente e i team saranno la prima applicazione in Office 365. La tabella seguente descrive in dettaglio la configurazione ad alto livello e le funzionalità degli utenti finali per i team per i servizi principali.

<table>
<thead>
<tr class="header">
<th>Elemento</th>
<th>Note</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Configurazione di Team tenant</td>
<td>Modalità solo teams, tutte le funzionalità di chat e chiamate sono solo in teams</td>
</tr>
<tr class="even">
<td>Chat/comunicazioni esterne in teams</td>
<td><p>Comunicazioni interne (intra Office 365 Organization) e chat esterna possibili da teams</p>
<p><em>Nota: le voci DNS devono essere configurate per l'accesso esterno. I record DNS Skype for business sono necessari anche se non si dispone di Skype for business locale o in Office 365 per consentire la Federazione con gli ambienti Lync e Skype for business.<br />
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">Record di sistema dei nomi di dominio esterni per Office 365</a></em></p></td>
</tr>
<tr class="odd">
<td><em>Creare e visualizzare riunioni in teams</em></td>
<td><p><em>In grado di creare riunioni tramite il componente aggiuntivo per Outlook</em></p>
<p><em>La funzionalità di accesso esterno e chiamata PSTN è disponibile con le licenze per i servizi di audioconferenza.<br />
Nota: l'accesso al calendario di team richiede Exchange 2016 CU3 + locale distribuito con Exchange Hybrid established: <a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">creare una distribuzione ibrida con la configurazione guidata ibrida</a><br />
Oltre alla configurazione ibrida di Exchange, stabilire l'autenticazione OAuth di Exchange: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">configurare l'autenticazione OAuth tra le organizzazioni Exchange e Exchange Online</a></em></p></td>
</tr>
<tr class="even">
<td>Funzionalità di chiamata<br />
VoIP/PSTN in teams</td>
<td><p>Il VoIP internamente ed esternamente al tenant è disponibile</p>
<p>I servizi PSTN possono essere configurati tramite il sistema telefonico Microsoft, oltre ad aggiungere un piano di chiamata Microsoft o un routing diretto.</p></td>
</tr>
<tr class="odd">
<td>Collaborazione di team e canali in teams</td>
<td><p>Per un'esperienza completa, incluse le caratteristiche di conformità, è necessario assegnare all'utente una licenza di SharePoint Online.</p>
<p>La migrazione dei siti di SharePoint locali esistenti non è obbligatoria.</p></td>
</tr>
<tr class="even">
<td>OneDrive for business (condivisione di file P2P)</td>
<td>OneDrive for business richiede a un utente di assegnare una licenza di SharePoint Online. Senza la condivisione di file peer-to-peer della licenza non sarà possibile.</td>
</tr>
<tr class="odd">
<td>Piattaforma dell'applicazione</td>
<td>Gli utenti potranno usare le app designate a loro disposizione in base ai criteri aziendali.<br />
Altre informazioni: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">impostazioni di amministrazione per le app in teams</a></td>
</tr>
<tr class="even">
<td>Caratteristiche di sicurezza e conformità</td>
<td><ul>
<li><p>Sono disponibili criteri di conservazione</p></li>
<li><p>eDiscovery e Legal detiene per la conformità ai messaggi di canale è supportato</p></li>
<li><p>Sono disponibili i criteri di prevenzione della perdita dei dati (DLP)</p></li>
</ul>
<p>Set di caratteristiche completo disponibile con Exchange Online, Exchange locale supporta la maggior parte di queste funzionalità, vedere <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">modalità di interazione tra Exchange e teams</a> per l'elenco completo.</p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a>Procedura di attivazione per le organizzazioni senza Skype for business o Lync Server

1.  Soddisfare i requisiti preliminari descritti nella sezione inizio qui sopra

2.  Cambiare il tenant in modalità solo Teams (solo per i tenant esistenti): [impostare le impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md).

3.  Configurare il tenant conformemente ai criteri aziendali/commerciali della società: [gestire le impostazioni di Microsoft teams per l'organizzazione](enable-features-office-365.md).

4.  Distribuire il client teams agli utenti: [ottenere clienti per Teams](get-clients.md)

5.  Guidare il programma di adozione  
    [Adottare Microsoft Teams](adopt-microsoft-teams-landing-page.md)
    
    [Elenco di controllo introduttivo di Microsoft teams adoption](teams-adoption-quick-start-checklist.md)

6.  Iniziare a pianificare lo spostamento di altri carichi di lavoro in Office 365

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a>Organizzazioni **<span class="underline">con</span>** Skype for business o Lync Server

Questo punto di partenza presuppone che l'organizzazione utilizzi Skype for business 2019 o 2015 + o Lync 2013 + server in locale. Esistono già linee guida estese per le organizzazioni che migrano dai server locali ai team e che dovrebbero essere seguite per questi scenari. Questa guida è specifica dello scenario in cui teams è la prima applicazione che si usa in Office 365. La tabella seguente descrive in dettaglio la configurazione ad alto livello e le funzionalità degli utenti finali per i team per i servizi principali.

<table>
<thead>
<tr class="header">
<th>Elemento</th>
<th>Note</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Configurazione di Team tenant</td>
<td>Modalità Isole</td>
</tr>
<tr class="even">
<td>Chat/comunicazioni esterne in teams</td>
<td>Interno solo all'interno del proprio tenant, la comunicazione esterna (Federazione) è tramite la distribuzione di Skype for business o Lync Server</td>
</tr>
<tr class="odd">
<td>Creare e visualizzare riunioni in teams</td>
<td><p>In grado di creare riunioni tramite il componente aggiuntivo per Outlook</p>
<p>La funzionalità di accesso esterno e chiamata PSTN è disponibile con le licenze per i servizi di audioconferenza.<br />
L'accesso al calendario teams richiede Exchange 2016 CU3 + locale distribuito con Exchange Hybrid established:<br />
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Creare una distribuzione ibrida con la configurazione guidata ibrida</a></p></td>
</tr>
<tr class="even">
<td>Funzionalità di chiamata<br />
VoIP/PSTN in teams</td>
<td><p>Il VoIP internamente al tenant è disponibile</p>
<p>I servizi PSTN o per i piani di chiamata non sono disponibili finché l'utente non viene spostato nell'esperienza solo Teams</p></td>
</tr>
<tr class="odd">
<td>Collaborazione di team e canali in teams</td>
<td><p>Per un'esperienza completa, incluse le caratteristiche di conformità, è necessario assegnare all'utente una licenza di SharePoint Online.</p>
<p>La migrazione dei siti di SharePoint locali esistenti non è obbligatoria.</p></td>
</tr>
<tr class="even">
<td>OneDrive for business (condivisione di file P2P)</td>
<td>OneDrive for business richiede a un utente di assegnare una licenza di SharePoint Online. Senza la condivisione di file della licenza per-to-peer non sarà possibile.</td>
</tr>
<tr class="odd">
<td>Piattaforma dell'applicazione</td>
<td>Gli utenti potranno usare le app designate a loro disposizione in base ai criteri aziendali.<br />
Altre informazioni: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">impostazioni di amministrazione per le app in teams</a></td>
</tr>
<tr class="even">
<td>Caratteristiche di sicurezza e conformità</td>
<td><ul>
<li><p>Sono disponibili criteri di conservazione</p></li>
<li><p>eDiscovery e Legal detiene per la conformità ai messaggi di canale è supportato</p></li>
<li><p>Sono disponibili i criteri di prevenzione della perdita dei dati (DLP)</p></li>
</ul>
<p>Set di caratteristiche completo disponibile con Exchange Online, Exchange locale supporta la maggior parte di queste funzionalità, vedere</p>
<p><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">Modalità di interazione tra Exchange e Teams</a></p>
<ul>
<li><p>per l'elenco completo</p></li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a>Procedura di attivazione per le organizzazioni con Skype for Business Server  

1.  Soddisfare i requisiti preliminari descritti nella sezione inizio qui sopra.

2.  Cambiare il tenant in modalità isole (per i tenant con provisioning dopo 9/1/2019, contattare il supporto tecnico per apportare questa modifica)  
    [Impostazione delle impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md)

3.  Configurare il tenant in conformità con le politiche aziendali/aziendali  
    [Gestire le impostazioni di Microsoft Teams per l'organizzazione](enable-features-office-365.md)

4.  Distribuire il client Teams  
    [Ottenere client per Teams](get-clients.md)

5.   Guidare il programma di adozione  
    [Adottare Microsoft Teams](adopt-microsoft-teams-landing-page.md)<br/>
    [Elenco di controllo introduttivo di Microsoft teams adoption](teams-adoption-quick-start-checklist.md)

6.  Iniziare a pianificare lo spostamento di altri carichi di lavoro in Office 365

7.  Creare Skype for business Hybrid e seguire i percorsi di aggiornamento consigliati per Skype for business e i server Lync  
    [Eseguire l'aggiornamento da Skype for business locale a teams](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a>Istruzione Closing

Microsoft teams può essere un attivatore per consentire all'organizzazione di riunire tutti i dipendenti, gli Information Worker e i lavoratori I FIRSTLINE su una singola piattaforma. [Puoi iniziare oggi stesso](https://products.office.com/microsoft-teams/group-chat-software) . [Qui](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)è possibile rimanere in contatto con tutti gli annunci più recenti e gli aggiornamenti mensili del prodotto.

Inoltre, dato che le aziende di tutto il mondo stanno gestendo l'attuale situazione COVID-19, abbiamo creato una serie di contenuti che ti aiuteranno a usare team per ottenere il massimo impatto nell'organizzazione.

  - Il nostro [impegno per i clienti durante COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)

  - [2 settimane in: cosa abbiamo imparato sul lavoro remoto](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [Distribuzione di riunioni ed eventi online](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [Aiutare le piccole e medie imprese a lavorare in remoto con Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [Trasformazione digitale di eventi Live: osservazioni di Bob Bejan dal Frontline](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [I principali 9 modi in cui Microsoft IT sta abilitando il lavoro remoto per i suoi dipendenti](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [Lavorare in remoto, rimanere al sicuro: suggerimenti per CISOs](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [Aiutare gli insegnanti e gli studenti a passare all'apprendimento remoto](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [Rimanere produttivi mentre si lavora in remoto con Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a>Informazioni di riferimento sui servizi di supporto

Teams si basa sui gruppi di Exchange Online, SharePoint Online, OneDrive for business e Microsoft 365 per dare agli utenti un'esperienza di Office 365 completamente integrata. Come indicato in precedenza, le squadre lavoreranno senza la distribuzione completa di questi servizi, con funzionalità limitate. Per altre informazioni sui team e i suoi requisiti preliminari, vedere il sito: [Benvenuti in teams](teams-overview.md).

Per informazioni specifiche su ognuno dei servizi elencati sopra, seguire i collegamenti seguenti:

  - Exchange Online viene usato per le funzionalità di calendario e per l'archiviazione dei messaggi peer-to-peer in teams. Per altre informazioni, vedere [come interagiscono Exchange e teams](exchange-teams-interact.md)

> [!IMPORTANT]
> Per l'interoperabilità teams con Exchange locale, è necessario configurare il nuovo protocollo di autenticazione OAuth di Exchange come descritto in [configurare l'autenticazione OAuth tra le organizzazioni Exchange e Exchange Online](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).

  - SharePoint viene usato per la condivisione di file nei canali, mentre/OneDrive for business viene usato per la condivisione di file in 1:1 o in chat di gruppo. Per altre informazioni, vedere [come interagire con SharePoint Online e OneDrive for business con Microsoft teams](sharepoint-onedrive-interact.md).

  - I [gruppi Microsoft 365](office-365-groups.md) vengono usati per la creazione e la gestione di team e canali.


## <a name="related-topics"></a>Argomenti correlati

[Poster di soluzioni di telefonia e architettura IT di Microsoft Teams](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[Pianificare la connettività ibrida tra Skype for Business Server e Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[Supportare i dipendenti remoti tramite Teams](support-remote-work-with-teams.md)

[Lavorare in remoto con Office 365](https://aka.ms/remote-work)
