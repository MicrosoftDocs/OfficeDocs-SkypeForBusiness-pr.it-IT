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
description: Usare queste indicazioni per implementare Microsoft Teams come primo carico di lavoro di Microsoft 365 o Office 365.
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: a30d5bed9443df3077ab7384cd8266d2f049148d
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909480"
---
# <a name="roll-out-microsoft-teams-first"></a>Implementare Microsoft Teams First

Microsoft Teams può aiutare i dipendenti a rimanere in contatto e a collaborare tra loro, soprattutto nel tempo attuale in cui il lavoro remoto è una realtà di dipendenti in tutto il mondo. La possibilità di chattare, fare video riunioni e collaborare ai documenti di Office all'interno di Teams può aiutare le aziende a rimanere produttivi. Sia che si sia una piccola azienda, una no profit o una grande organizzazione, è possibile iniziare a usare Teams come primo carico di lavoro all'interno della famiglia di prodotti Microsoft 365 o Office 365 prima di distribuire qualsiasi altra app o servizio di Office.

Questo articolo illustra nel dettaglio le considerazioni da tenere in considerazione per l'approccio "Teams First".

> [!IMPORTANT]
> Anche se Teams può essere il primo carico di lavoro distribuito nel cloud dell'organizzazione, la distribuzione di Teams dovrebbe fare parte della strategia di distribuzione cloud complessiva.

Se sono già stati implementazioni altri servizi di Microsoft 365 o Office 365 e Teams rappresenta il prossimo carico di lavoro da implementare (invece del primo), iniziare da [Come implementare Teams.](How-to-roll-out-teams.md)

## <a name="start-here"></a>Iniziare da qui

Per iniziare con la distribuzione Teams First, è necessario soddisfare almeno alcuni prerequisiti. L'elenco seguente mostra cosa è necessario avere in posizione per l'organizzazione prima che Teams possa essere abilitato:

1.  Un'organizzazione di Microsoft 365 o Office 365 configurata con il nome di dominio

2.  Connettività di Azure Active Directory (connessione AAD) o soluzione di sincronizzazione delle identità cloud simile, con tutti gli attributi obbligatori sincronizzati con il tenant  
    Per informazioni sugli attributi sincronizzati con la sincronizzazione AAD, leggere la sincronizzazione [di Azure AD Connect: attributi sincronizzati con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)

3.  Licenze utente appropriate assegnate a Teams  
    Per informazioni sulle licenze di Teams, leggere la [descrizione del servizio Microsoft Teams.](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

4.  Rete dell'organizzazione preparata per Teams  
    Per informazioni sulla preparazione della rete, vedere [Preparare la rete dell'organizzazione per Teams.](prepare-network.md)

5.  Consentire l'accesso di rete a Exchange, Sharepoint e OneDrive for Business in Microsoft 365 o Office 365: URL e intervalli di indirizzi IP per [Office 365.](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)

> [!NOTE]
> I tenant creati dopo il 1° settembre 2019 sono disponibili solo in modalità Teams.
> 
> [!IMPORTANT]
> Se è stato distribuito Skype for Business Server ed è stato eseguito il provisioning del tenant DOPO il 1° settembre 2019, contattare il supporto per abilitare le funzionalità di coesistenza per Teams. Assicurati che il "criterio di aggiornamento a livello di organizzazione" sia impostato sulla "modalità <span class="underline">Isola"</span> prima di assegnare le licenze di Teams a un utente.

## <a name="migration-starting-points"></a>Punti di partenza della migrazione

Il viaggio in Microsoft 365 o Office 365 e le funzionalità disponibili in Teams dipendono dal punto di partenza e dalla presenza di Skype for Business o Lync Server locale. Le sezioni seguenti illustrano in dettaglio le funzionalità e le opzioni di configurazione di base oltre ai prerequisiti descritti in precedenza. Gli scenari di partenza sono stati suddivisi negli argomenti seguenti:

**Configurazione di Tenant Teams:** le modalità tenant e utente vengono usate per controllare il comportamento del destinatario. Queste impostazioni possono essere assegnate a livello di tenant o di utente in un'organizzazione. Per ulteriori informazioni, vedere [Coesistenza con Skype for Business.](coexistence-chat-calls-presence.md)

**Comunicazione tramite chat o esterna in Teams:** i servizi di chat fanno riferimento a conversazioni peer-to-peer o di chat di gruppo all'interno e all'organizzazione o esternamente all'organizzazione. La comunicazione esterna è detta anche federazione in Skype for Business.

**Creare e visualizzare riunioni in Teams:** un utente può sempre creare riunioni online tramite il componente aggiuntivo Outlook Teams e l'accesso con accesso remoto PSTN è disponibile in tutti gli scenari una volta che l'utente ha una licenza. Teams e Skype for Business archiviano le informazioni del calendario nella cassetta postale di Exchange dell'utente. Il server Exchange locale deve Exchange Server 2016 CU3 o versione precedente perché il client Teams possa interagire con la cassetta postale dell'utente. Senza accesso alla cassetta postale di Exchange, l'icona calendario in Teams non verrà visualizzata e l'utente non sarà in grado di visualizzare, creare o modificare riunioni nel client Teams.

**Funzionalità di chiamata VoIP/PSTN in Teams:** le chiamate possono essere Voice over IP (VoIP) o PSTN (Public Switched Telephone Network). La connettività VoIP avviene a livello nativo tra i client di Teams, mentre la connettività PSTN avviene quando un utente compone un numero di telefono esterno.  

Teams supporta due tipi di connettività PSTN. Piano per chiamate Microsoft, quando Microsoft fornisce un'infrastruttura telefonica comprensiva del numero di telefono di un utente o della configurazione di instradamento diretto, in cui il cliente fornisce la connettività telefonica su un Session Border Controller (SBC) per l'utente di Teams.  
Per saperne di più, leggi Quale piano per chiamate è la scelta giusta [per te?](calling-plan-landing-page.md) [e Instradamento diretto del Sistema telefonico.](direct-routing-landing-page.md)

**Collaborazione tra team e canali in Teams:** In Teams, i team sono gruppi di persone che si riuniranno per lavoro, progetti o interessi comuni. I team sono fatti di canali. Ogni canale è basato su un argomento, ad esempio "Eventi del team", il nome di un reparto o solo per divertimento. Nei canali puoi tenere riunioni, tenere conversazioni e lavorare insieme ai file. Durante la collaborazione

**OneDrive for Business (condivisione di file P2P) in Teams:** All'esterno di Teams e canali, gli utenti di Teams possono condividere file peer-to-peer utilizzando OneDrive for Business o altri programmi di file di condivisione P2P come File Citrix, DropBox, Box e Google Drive. Per OneDrive for Business, è necessario che a un utente sia assegnata una licenza di SharePoint Online.

**Piattaforma** dell'applicazione: le app forniscono strumenti avanzati per l'organizzazione per ottenere il maggior numero di informazioni da Teams. Queste app combinano le funzionalità di schede, estensioni di messaggistica, connettori e bot forniti da Microsoft, creati da terze parti o da sviluppatori dell'organizzazione.

**Caratteristiche di sicurezza e conformità:** Teams include un'ampia gamma di informazioni utili per le aree di conformità, tra cui criteri di conservazione, prevenzione della perdita dei dati (DLP), eDiscovery e blocco a livello legale per canali, chat e file, ricerca nel log di controllo. Per saperne di più, [leggi Sicurezza e conformità in Microsoft Teams.](security-compliance-overview.md)  

> [!NOTE]
> Le caratteristiche di Advance eDiscovery richiedono una licenza E5.

[Confrontare le opzioni di licenza.](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)

Leggere [come interagiscono Exchange e Microsoft Teams](exchange-teams-interact.md) per sapere quali funzionalità di conformità sono disponibili nello scenario.

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a>Organizzazioni **<span class="underline">senza</span>** Skype for Business o Lync Server

Questo punto di partenza presuppone che l'organizzazione non utilizzi attualmente Skype for Business o Lync Server e Teams sarà la prima applicazione in Microsoft 365 o Office 365. La tabella seguente dettaglia la configurazione di alto livello e le funzionalità per gli utenti finali di Teams per i servizi di base.

<table>
<thead>
<tr class="header">
<th>Elemento</th>
<th>Note</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Configurazione di Tenant Teams</td>
<td>Modalità Solo Teams, tutte le funzionalità di chat e chiamate sono disponibili solo in Teams.</td>
</tr>
<tr class="even">
<td>Chat/Comunicazione esterna in Teams</td>
<td><p>Comunicazioni interne (interne a Microsoft 365 o Office 365) e chat esterne da Teams.</p>
<p><em>Nota: le voci DNS devono essere configurate per l'accesso esterno. I record DNS di Skype for Business sono necessari anche se skype for Business non è installato in locale o in Microsoft 365 o Office 365, per consentire la federazione con ambienti Lync e Skype for Business:<br />
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">Record DNS (Domain Name System) esterni</a></em></p></td>
</tr>
<tr class="odd">
<td>Creare e visualizzare riunioni in Teams</td>
<td><p>Possibilità di creare riunioni interne ed esterne tramite il componente aggiuntivo Outlook.</p>
<p>Con le licenze di Audioconferenza è disponibile la funzionalità Chiamata in ingresso e uscita PSTN.</p>
<p>L'accesso al calendario di Teams richiede Exchange 2016 CU3+ locale distribuito con Exchange ibrido stabilito: creare una distribuzione ibrida con <a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">la procedura guidata Configurazione ibrida.</a> </p>
<p>Oltre alla configurazione ibrida di Exchange, stabilire l'autenticazione OAuth di Exchange: configurare l'autenticazione OAuth tra le organizzazioni di Exchange ed <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help"> Exchange Online".</p>

</p></td>
</tr>
<tr class="even">
<td>Funzionalità di chiamata<br />
VoIP/PSTN in Teams</td>
<td><p>VoIP sia all'interno che all'esterno del tenant è disponibile.</p>
<p>I servizi PSTN possono essere configurati tramite il Sistema telefonico Microsoft, oltre all'aggiunta di un piano per chiamate Microsoft o di instradamento diretto.</p></td>
</tr>
<tr class="odd">
<td>Collaborazione tra team e canali in Teams</td>
<td><p>Per un'esperienza completa, incluse le caratteristiche di conformità, è necessario assegnare una licenza di SharePoint Online all'utente.</p>
<p>Non è richiesta la migrazione di siti di SharePoint locali esistenti.</p></td>
</tr>
<tr class="even">
<td>OneDrive for Business (condivisione di file P2P)</td>
<td>OneDrive for Business richiede l'assegnazione di una licenza di SharePoint Online a un utente. Senza questa licenza non sarà possibile condividere i file peer-to-peer.</td>
</tr>
<tr class="odd">
<td>Piattaforma dell'applicazione</td>
<td>Gli utenti potranno usare le app designate per loro disponibili in base ai criteri della società.<br />
Altre informazioni qui: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Impostazioni di amministratore per le app in Teams</a></td>
</tr>
<tr class="even">
<td>Caratteristiche di sicurezza e conformità</td>
<td><ul>
<li><p>Sono disponibili criteri di conservazione.</p></li>
<li><p>Sono supportati eDiscovery e blocco a livello legale per la conformità ai messaggi di canale.</p></li>
<li><p>Sono disponibili criteri di prevenzione della perdita dei dati.</p></li>
</ul>
<p>Set di caratteristiche completo disponibile con Exchange Online; Exchange locale supporta la maggior parte di queste caratteristiche. Per un elenco completo, vedere come <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">interagiscono Exchange e Teams.</a></p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a>Procedura di abilitazione per le organizzazioni senza Skype for Business o Lync Server

1.  Ecco i prerequisiti dettagliati nella sezione Iniziare qui sopra

2.  Passa il tenant in modalità Solo Teams (solo per i tenant esistenti): [Impostazione delle impostazioni di coesistenza e aggiornamento.](setting-your-coexistence-and-upgrade-settings.md)

3.  Configurare il tenant in base ai criteri aziendali: gestire le impostazioni di [Microsoft Teams per l'organizzazione.](enable-features-office-365.md)

4.  Distribuire il client teams agli utenti: [Ottenere i client per Teams](get-clients.md)

5.  Guidare il programma di adozione  
    [Adottare Microsoft Teams](adopt-microsoft-teams-landing-page.md)
    
    [Elenco di controllo introduttivo per l'adozione di Microsoft Teams](teams-adoption-quick-start-checklist.md)

6.  Iniziare a pianificare lo spostamento di altri carichi di lavoro in Microsoft 365 o Office 365

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a>Organizzazioni **<span class="underline">con</span>** Skype for Business o Lync Server

Da questo punto di partenza si presuppone che l'organizzazione utilizzi il server Skype for Business 2019 o 2015+ o Lync 2013+ locale. Sono già disponibili indicazioni per le organizzazioni che ese stanno eseguendo la migrazione da server locali a Teams e devono essere seguite per questi scenari. Queste indicazioni sono specifiche per lo scenario che Teams è la prima applicazione utilizzata in Microsoft 365 o Office 365. La tabella seguente dettaglia la configurazione di alto livello e le funzionalità per gli utenti finali di Teams per i servizi di base.

<table>
<thead>
<tr class="header">
<th>Elemento</th>
<th>Note</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Configurazione di Tenant Teams</td>
<td>Modalità Isole.</td>
</tr>
<tr class="even">
<td>Chat/Comunicazione esterna in Teams</td>
<td>Interna solo all'interno del proprio tenant, la comunicazione esterna (federazione) avviene tramite la distribuzione di Skype for Business o Lync Server.</td>
</tr>
<tr class="odd">
<td>Creare e visualizzare riunioni in Teams</td>
<td><p>Possibilità di creare riunioni interne ed esterne tramite il componente aggiuntivo Outlook.</p>
<p>Con le licenze di Audioconferenza è disponibile la funzionalità Chiamata in ingresso e uscita PSTN.</p>
<p>L'accesso al calendario di Teams richiede Exchange 2016 CU3+ locale distribuito con Exchange ibrido stabilito:<br />
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Creare una distribuzione ibrida con la procedura guidata Configurazione ibrida.</a></p>
<p>L'amministratore può controllare il componente aggiuntivo Outlook di Skype for Business tramite l'attributo PreferredMeetingProviderForIslandsMode dei criteri riunione di Teams:<a href="https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy.</a></p> 
</td>
</tr>
<tr class="even">
<td>Funzionalità di chiamata<br />
VoIP/PSTN in Teams</td>
<td><p>VoIP internamente al tenant è disponibile.</p>
<p>I servizi PSTN o Piani per chiamate non sono disponibili finché l'utente non passa all'esperienza Solo Teams.</p></td>
</tr>
<tr class="odd">
<td>Collaborazione tra team e canali in Teams</td>
<td><p>Per un'esperienza completa, incluse le caratteristiche di conformità, è necessario assegnare una licenza di SharePoint Online all'utente.</p>
<p>Non è richiesta la migrazione di siti di SharePoint locali esistenti.</p></td>
</tr>
<tr class="even">
<td>OneDrive for Business (condivisione di file P2P)</td>
<td>OneDrive for Business richiede l'assegnazione di una licenza di SharePoint Online a un utente. Senza questa licenza non sarà possibile condividere i file per peer.</td>
</tr>
<tr class="odd">
<td>Piattaforma dell'applicazione</td>
<td>Gli utenti potranno usare le app designate per loro disponibili in base ai criteri della società.<br />
Altre informazioni qui: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Impostazioni di amministratore per le app in Teams</a></td>
</tr>
<tr class="even">
<td>Caratteristiche di sicurezza e conformità</td>
<td><ul>
<li><p>Sono disponibili criteri di conservazione.</p></li>
<li><p>Sono supportati eDiscovery e blocco a livello legale per la conformità ai messaggi di canale.</p></li>
<li><p>Sono disponibili criteri di prevenzione della perdita dei dati.</p></li>
</ul>
<p>Set di caratteristiche completo disponibile con Exchange Online; Exchange locale supporta la maggior parte di queste caratteristiche. Per un elenco completo, vedere <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">l'interazione tra Exchange e Teams.</a></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a>Procedura di abilitazione per le organizzazioni con Skype for Business Server  

1.  Ecco i prerequisiti dettagliati nella sezione Iniziare qui sopra.

2.  Passare alla modalità Isole (per i tenant di cui è stato effettuato il provisioning DOPO l'1/9/2019, contatta il supporto tecnico per apportare questa modifica)  
    [Impostazione delle impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md)

3.  Configurare il tenant in base ai criteri aziendali e aziendali  
    [Gestire le impostazioni di Microsoft Teams per l'organizzazione](enable-features-office-365.md)

4.  Distribuire il client di Teams  
    [Ottenere client per Teams](get-clients.md)

5.   Guidare il programma di adozione  
    [Adottare Microsoft Teams](adopt-microsoft-teams-landing-page.md)<br/>
    [Elenco di controllo introduttivo per l'adozione di Microsoft Teams](teams-adoption-quick-start-checklist.md)

6.  Iniziare a pianificare lo spostamento di altri carichi di lavoro in Microsoft 365 o Office 365

7.  Stabilire una distribuzione ibrida di Skype for Business e seguire i percorsi di aggiornamento consigliati per i server Skype for Business e Lync  
    [Eseguire l'aggiornamento da Skype for Business locale a Teams](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a>Istruzione di chiusura

Microsoft Teams può essere un abilitazione per l'organizzazione a riunire tutti i dipendenti, information worker e frontline worker su un'unica piattaforma. È possibile [iniziare oggi](https://products.office.com/microsoft-teams/group-chat-software) stesso. Puoi rimanere in contatto con tutti gli ultimi annunci e gli aggiornamenti mensili dei [prodotti qui.](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)

Inoltre, poiché le aziende di tutto il mondo gestiscono l'attuale situazione di COVID-19, abbiamo creato una serie di contenuti che ti aiuteranno a utilizzare Teams per il massimo impatto nell'organizzazione.

  - Il [nostro impegno verso i clienti durante IL COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)

  - [2 settimane in: ciò che abbiamo appreso sul lavoro remoto](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [Fornire riunioni ed eventi online](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [Aiutare le piccole e medie imprese a lavorare in remoto con Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [Trasformazione digitale degli eventi live: osservazioni di Bob Bejan dal fronte](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [I principali 9 modi in cui Microsoft IT sta abilitando il lavoro remoto per i suoi dipendenti](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [Lavorare in remoto e restare al sicuro, suggerimenti per CISO](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [Aiutare insegnanti e studenti a passare all'apprendimento remoto](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [Rimanere produttivi mentre si lavora in remoto con Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a>Informazioni di riferimento per i Servizi di supporto tecnico

Teams si basa su Exchange Online, SharePoint Online, OneDrive for Business e Gruppi di Microsoft 365 per offrire agli utenti un'esperienza microsoft 365 o Office 365 completamente integrata. Come descritto in precedenza, Teams funzionerà senza la distribuzione completa di questi servizi, con funzionalità limitate. Per saperne di più su Teams e sui prerequisiti, vedere: [Benvenuto in Teams.](teams-overview.md)

Per informazioni specifiche su ognuno dei servizi elencati sopra, seguire i collegamenti seguenti:

  - Exchange Online viene usato per le funzionalità di calendario e per l'archiviazione di messaggi peer-to-peer in Teams. Per altre informazioni, vedere [Come interagiscono Exchange e Teams](exchange-teams-interact.md)

> [!IMPORTANT]
> Per l'interoperabilità di Teams con Exchange locale, è necessario configurare il nuovo protocollo di autenticazione OAuth di Exchange come descritto in Configurare l'autenticazione OAuth tra le organizzazioni di Exchange ed [Exchange Online.](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

  - SharePoint viene usato per la condivisione di file nei canali, mentre /OneDrive for Business viene usato per la condivisione di file in una chat 1:1 o di gruppo. Per altre informazioni, vedere [Come interagiscono SharePoint Online e OneDrive for Business con Microsoft Teams.](sharepoint-onedrive-interact.md)

  - [I gruppi di Microsoft 365 vengono](office-365-groups.md) usati per la creazione/gestione di team e canali.


## <a name="related-topics"></a>Argomenti correlati

[Poster di soluzioni di telefonia e architettura IT di Microsoft Teams](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[Pianificare la connettività ibrida tra Skype for Business Server e Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[Supportare lavoratori remoti con Teams](support-remote-work-with-teams.md)

[Lavorare in remoto con Microsoft 365](https://aka.ms/remote-work)
