---
title: Autorizzazioni e considerazioni sulle app di Microsoft Teams
author: rmw2890
ms.author: rowille
manager: serdars
ms.date: 10/18/2018
ms.topic: conceptual
ms.service: msteams
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
search.appverid: MET150
ms.reviewer: rowille
description: Informazioni sulle app per i dati e le autorizzazioni richieste dall'organizzazione.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 598fd2d9dc8c8942a2d82e136c8367afa4d8495e
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2019
ms.locfileid: "36184372"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Autorizzazioni e considerazioni sulle app di Microsoft Teams

Le app di Microsoft teams sono un modo per aggregare una o più funzionalità in un _pacchetto dell'app_ che può essere installato, aggiornato e disinstallato. Le funzionalità includono:

- Bot
- Estensioni della messaggistica
- Schede
- Connettori

Le app vengono consentite dagli utenti e gestite da una prospettiva politica. Tuttavia, per la maggior parte, le autorizzazioni e il profilo di rischio di un'app sono definiti dalle autorizzazioni e dai profili di rischio delle funzionalità contenute nell'app. Questo articolo si basa quindi sulle autorizzazioni e sulle considerazioni a livello di funzionalità.

Le autorizzazioni elencate di seguito in lettere maiuscole, ad esempio RECEIVE_MESSAGE e REPLYTO_MESSAGE, non vengono visualizzate in nessuna posizione nella [documentazione dello sviluppatore di Microsoft teams](https://aka.ms/teamsdevdocs) o nelle [autorizzazioni per Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference). Sono semplicemente una scorciatoia descrittiva ai fini di questo articolo.


|    |     |
|-----------|------------|
| ![Icona che descrive un punto decisionale](media/audio_conferencing_image7.png) <br/>Punto decisionale|<ul><li>Usare le tabelle seguenti come guida per individuare le autorizzazioni richieste dalle app che si stanno esaminando.</li></ul> |
| ![Icona che descrive il passaggio successivo](media/audio_conferencing_image9.png)<br/>Passaggio successivo|<ul><li>Eseguire ricerche nell'app o nel servizio stesso per decidere se si vuole consentire l'accesso all'interno dell'organizzazione. Ad esempio, i bot inviano e ricevono messaggi dagli utenti e, ad eccezione dei bot line-of-business aziendali, sono situati al di fuori del limite di conformità. Di conseguenza, qualsiasi app che includa un bot richiede le autorizzazioni e ha il profilo di rischio, come minimo. </li></ul>|

## <a name="global-app-permissions-and-considerations"></a>Autorizzazioni e considerazioni sulle app globali

<table>
  <tr>
    <th width="25%">Autorizzazioni necessarie</th>
    <th width="25%">Autorizzazioni facoltative</th>
    <th width="50%">Considerazioni</th>
  </tr>
  <tr>
    <td valign="top">Nessuno</td>
    <td valign="top">Nessuno</td>
    <td valign="top">Un'app deve rivelare i dati che usa e i dati usati per i collegamenti alle condizioni d'uso e ai criteri di privacy.</td>
  </tr>
</table>

## <a name="bots-and-messaging-extensions"></a>Bot e estensioni di messaggistica

<table>
 <thead>
  <tr>
    <th width="0.5%"></th>
    <th width="24.5%">Autorizzazioni necessarie</th>
    <th width="25%">Autorizzazioni facoltative</th>
    <th width="50%">Considerazioni</th>
  </tr>
</thead>
<tbody>
   <tr>
    <td valign="top" colspan="2"><ul><li>   RECEIVE_MESSAGE, REPLYTO_MESSAGE. Il bot può ricevere messaggi dagli utenti e rispondere. <sup>1</sup></li><li>POST_MESSAGE_USER. Dopo che un utente ha inviato un messaggio a un bot, il bot può inviare messaggi diretti dall'utente (detti anche <em>messaggi proattivi</em>) in qualsiasi momento.</li><li>GET_CHANNEL_LIST. I bot aggiunti ai team possono ottenere un elenco di nomi e ID dei canali in un team.</li></ul></td>
    <td valign="top"><ul><li>Identità. Quando&#39;s usato in un canale, l'app&#39;i bot possono accedere alle informazioni di base sulle identità dei membri del team (nome, cognome, nome dell'entità utente [UPN], indirizzo di posta elettronica); quando&#39;s viene usato in una chat personale o di gruppo, il bot può accedere alle stesse informazioni per gli utenti.</li><li> POST_MESSAGE_TEAM. Consente a un'app&#39;i bot di inviare messaggi diretti (proattivi) a qualsiasi membro del team in qualsiasi momento, anche se l'utente non ha mai parlato prima con il bot.</li><li>Le autorizzazioni seguenti non sono esplicite, ma sono implicite in base a RECEIVE_MESSAGE e REPLYTO_MESSAGE e agli ambiti in cui è possibile usare i bot, dichiarati nel manifesto: <ul><li>RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</li><li>RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT</li><li>RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</li></ul><li>SEND_FILES, RECEIVE_FILES. <sup>2</sup> controlla se un bot può inviare e ricevere file in chat personali (non ancora supportati per la chat di gruppo o i canali).</li></ul></td>
    <td valign="top"><ul><li>I bot hanno accesso solo ai team a cui sono stati aggiunti&#39;o agli utenti che li hanno installati.</li><li>I bot ricevono solo i messaggi in cui vengono&#39;menzionati esplicitamente dagli utenti. Questi dati lasciano la rete aziendale.</li><li>    I bot possono solo rispondere alle conversazioni in cui&#39;menzionato.</li><li>Dopo che un utente ha conversato con un bot, se il bot archivia l'ID utente&#39;s, può inviare messaggi diretti dall'utente in qualsiasi momento. </li><li>È teoricamente possibile che i messaggi di bot contengano collegamenti a siti di phishing o malware, ma i bot possono essere bloccati dall'utente, dall'amministratore del tenant o globalmente da Microsoft. </li><li>Un bot può recuperare (e potrebbe archiviare) informazioni di identità molto basilari per i membri del team a cui è stata aggiunta l'app o per singoli utenti in chat personali o di gruppo. Per ottenere altre informazioni su questi utenti, il bot deve richiedere l'accesso a Azure Active Directory (Azure AD). </li><li>I bot possono recuperare (e potrebbero archiviare) l'elenco dei canali in un team; questi dati lasciano la rete aziendale. </li><li>Quando un file viene inviato a un bot, il file esce dalla rete aziendale. L'invio e la ricezione di file richiede l'approvazione dell'utente per ogni file. </li><li>Per impostazione predefinita, i bot Don&#39;t hanno la possibilità di agire per conto dell'utente, ma i bot possono chiedere agli utenti di effettuare l'accesso; non appena l'utente accede, il bot avrà un token di accesso con cui può eseguire altre operazioni. Esattamente ciò che questi elementi aggiuntivi dipendono dal bot e dalla posizione in cui l'utente accede: un bot è un'app Azure AD registrata <a href="https://apps.dev.microsoft.com/">https://apps.dev.microsoft.com/</a> e può avere un proprio set di autorizzazioni.</li><li>I bot vengono informati ogni volta che gli utenti vengono aggiunti o eliminati da un team.</li><li>Bots Don&#39;t vedere gli utenti&#39; indirizzi IP o altre informazioni sul referrer. Tutte le informazioni provengono da Microsoft. (C'è un'eccezione: se un bot implementa la propria esperienza di accesso, l'interfaccia utente di accesso vedrà gli utenti&#39; gli indirizzi IP e le informazioni sul referrer.)</li><li>Le estensioni della messaggistica, invece, vedono gli utenti&#39; indirizzi IP e informazioni sul referrer.</li><li>Le linee guida per le app (e il processo di revisione di AppSource) richiedono discrezionalità nella pubblicazione di messaggi di chat personali per gli utenti (tramite l'autorizzazione POST_MESSAGE_TEAM) per scopi validi. In caso di abuso, gli utenti possono bloccare il bot, gli amministratori del tenant possono bloccare l'app e Microsoft può bloccare i bot centralmente, se necessario.</li></ul></td>
</tr>
</tbody>
<tfoot>
<tr><td align="right"><sup>1</sup></td><td colspan="3">Alcuni bot inviano solo messaggi (POST_MESSAGE_USER). Essi&#39;ri chiamati &quot;bot di sola&quot; notifica, ma il termine doesn&#39;t si riferisce a ciò che un bot è autorizzato o non è autorizzato a eseguire, significa che il bot doesn&#39;t vuole esporre un'esperienza di conversazione. Teams USA questo campo per disabilitare la funzionalità nell'interfaccia utente che verrebbe normalmente abilitata; il bot isn&#39;t limitato in ciò che&#39;s consentito di fare rispetto ai bot che espongono un'esperienza di conversazione.</td></tr>
<tr><td align="right"><sup>2</sup></td><td colspan="3">Regolato dalla proprietà <code>supportsFiles</code> booleana nell'oggetto bot nel file manifest. JSON per l'app.</td>
</tr>
</tfoot>
</table>

> [!Note]
> <ul><li>Se un bot ha un proprio accesso, la prima volta che l'utente accede a un'esperienza di consenso diversa è la seconda:</li><li>Attualmente, le autorizzazioni di Azure AD associate a qualsiasi funzionalità all'interno di un'app Teams (bot, TAB, Connector o Messaging Extension) sono completamente separate dalle autorizzazioni per i team elencate qui.</li></ul>


## <a name="tabs"></a>Schede

Una scheda è un sito Web che si trova all'interno di teams.

<table>
  <tr>
    <th width="25%">Autorizzazioni necessarie</th>
    <th width="25%">Autorizzazioni facoltative</th>
    <th width="50%">Considerazioni</th>
  </tr>
  <tr>
    <td valign="top">SEND_AND_RECEIVE_WEB_DATA</td>
    <td valign="top">Nessuno (attualmente).</td>
    <td valign="top"><ul><li>Il profilo di rischio per una tabulazione è quasi identico a quello stesso sito Web in uso in una scheda del browser. </li><li>Una scheda ottiene anche il contesto in cui&#39;s in corso, incluso il nome di accesso e l'UPN dell'utente corrente, l'ID oggetto Azure AD per l'utente corrente, l'ID del gruppo Office 365 in cui si trova (se si tratta di un team) , l'ID tenant e le impostazioni locali correnti dell'utente. Tuttavia, per eseguire il mapping di questi ID a un utente&#39;informazioni s, la scheda dovrebbe rendere l'accesso dell'utente ad Azure AD.</li></ul></td>
  </tr>
  </table>

## <a name="connectors"></a>Connettori

Un connettore invia i messaggi a un canale quando si verificano gli eventi in un sistema esterno.

  <table>
  <tr>
    <th width="25%">Autorizzazioni necessarie</th>
    <th width="25%">Autorizzazioni facoltative</th>
    <th width="50%">Considerazioni</th>
  </tr>
  <tr>
    <td valign="top">POST_MESSAGE_CHANNEL</td>
    <td valign="top">REPLYTO_CONNECTOR_MESSAGE. Alcuni connettori supportano <em>i messaggi di azione</em>, che consentono agli utenti di inserire risposte mirate al messaggio del connettore, ad esempio aggiungendo una risposta a un problema di GitHub o aggiungendo una data a una scheda Trello.</td>
    <td valign="top"><ul><li>Il sistema che invia messaggi di connettore non&#39;sapere a chi&#39;o a chi riceve i messaggi: non vengono divulgate informazioni sul destinatario. (Microsoft è il destinatario effettivo, non il tenant; Microsoft esegue il post effettivo sul canale.</li><li>Nessun dato esce dalla rete aziendale quando i messaggi del connettore vengono inseriti in un canale.</li><li>Connettori che supportano i messaggi actionable (autorizzazione REPLYTO_CONNECTOR_MESSAGE) anche Don&#39;t vedere l'indirizzo IP e informazioni sul referrer; Queste informazioni vengono inviate a Microsoft e quindi instradate agli endpoint HTTP precedentemente registrati con Microsoft nel portale dei connettori.</li><li>Ogni volta che un connettore è configurato per un canale, viene creato un URL univoco per l'istanza del connettore. Se l'istanza del connettore viene eliminata, l'URL non può più essere usato.</li><li>I messaggi del connettore possono&#39;t contengono file allegati.</li><li>L'URL dell'istanza del connettore deve essere considerato segreto/riservato: chiunque disponga di tale URL può inserire un post, ad esempio un indirizzo di posta elettronica. Di conseguenza, c'&#39;un rischio di posta indesiderata o collegamenti a siti di phishing o malware. Se ciò dovesse accadere, i proprietari del team possono eliminare l'istanza del connettore.</li><li>Se il servizio che invia i messaggi del connettore dovesse essere compromesso e iniziare a inviare collegamenti di posta indesiderata/phishing/malware, un amministratore del tenant può impedire la creazione di nuove istanze di connettori e Microsoft può bloccarle centralmente.</li></ul></td>
  </tr>
</table>

> [!Note]
> Attualmente non è possibile sapere quali connettori supportano i messaggi actionable (autorizzazione REPLYTO_CONNECTOR_MESSAGE).


## <a name="outgoing-webhooks"></a>Webhook in uscita

I webhook in _uscita_ vengono creati al volo dai proprietari del team o dai membri del team se sideload è abilitato per un tenant. Non sono funzionalità delle app Teams; Queste informazioni sono incluse per la completezza.

<table>
  <tr>
    <th width="25%">Autorizzazioni necessarie</th>
    <th width="25%">Autorizzazioni facoltative</th>
    <th width="50%">Considerazioni</th>
  </tr>
    <tr>
    <td valign="top">RECEIVE_MESSAGE, REPLYTO_MESSAGE. Può ricevere messaggi dagli utenti e rispondere.</td>
    <td valign="top">Nessuno</td>
    <td valign="top"><ul><li>I webhook in uscita sono simili ai bot, ma hanno meno privilegi. Devono essere esplicitamente menzionati, proprio come i bot.</li><li>Quando viene registrato un webhook in uscita, viene generato un <em>segreto</em> , che consente al webhook in uscita di verificare che il mittente sia Microsoft teams in contrapposizione a un utente malintenzionato. Questo segreto deve rimanere segreto; chiunque abbia accesso può rappresentare Microsoft teams. Se il segreto è compromesso, il webhook in uscita può essere eliminato e ricreato e verrà generato un nuovo segreto.</li><li>Anche se&#39;s possibile creare un webhook in uscita che doesn&#39;t convalidare il segreto, è consigliabile opporsi.</li><li>Oltre a ricevere e rispondere ai messaggi, i webhook in uscita possono&#39;fare molto: possono&#39;t inviare messaggi in modo proattivo, possono&#39;inviare o ricevere file, non possono&#39;eseguire altre operazioni che i bot possono eseguire, tranne che per ricevere e rispondere ai messaggi.</li></ul></td>
  </tr>
</table>
