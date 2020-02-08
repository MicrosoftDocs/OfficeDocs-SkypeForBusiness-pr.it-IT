---
title: Problemi noti di Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 6/25/2019
ms.topic: troubleshooting
ms.service: msteams
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: marcl
audience: admin
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
description: Elenco corrente dei problemi noti riguardanti l’interfaccia di amministrazione e l'app client di Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1f18bd8fa85ce07596fe36106ea97ef36e698a78
ms.sourcegitcommit: 8e2fa7b744d0a174b699ae7298d4688b971eeff3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/07/2020
ms.locfileid: "41845147"
---
# <a name="known-issues-for-microsoft-teams"></a>Problemi noti di Microsoft Teams

Questo articolo elenca i problemi noti di Microsoft Teams per area funzionale.

## <a name="administration"></a>Amministrazione

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|I criteri di EAF di EMET (Enhanced Mitigation Experience Toolkit) possono identificare erroneamente le ottimizzazioni della sandbox di Chromium come minacce. <br/> |È stato riscontrato un problema con la sandbox di Chromium, in cui i criteri di EAF (Export Table Access Filtering) di EMET (Advanced Mitigation Experience Toolkit) e ATP (Advanced Threat Protection) di Windows Defender possono identificare erroneamente le ottimizzazioni della sandbox di Chromium come minacce. A causa di ciò, Teams non funziona correttamente.  <br/> | Per ovviare al problema, si consiglia di disattivare il filtro EAF per Teams. Per maggiori informazioni sul problema, consultare le [linee guida sulle mitigazioni di EMET](https://support.microsoft.com/help/2909257/emet-mitigations-guidelines) Per ulteriori informazioni sui criteri di EAF e di ATP di Windows Defender, vedere [Abilitare la protezione da exploit](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-exploit-protection) <br/> |11/10/2018 <br/> |

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Non è possibile aggiungere membri ai team quando UsersPermissionToReadOtherUsersEnabled è impostato su false  <br/> |Se il suddetto valore è impostato su falso in AAD, il cliente non è in grado di aggiungere membri esterni o interni in Microsoft Teams e viene visualizzato il seguente messaggio di errore: "Impossibile aggiungere membro. Si è verificato un problema. Riprovare più tardi." Tuttavia, i membri possono essere aggiunti direttamente ai gruppi di Office 365.    <br/> |Modificare l’opzione su true in AAD.  <br/> |10/04/2018  <br/> |

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|La gestione amministratore dei connettori a livello di tenant non è più disponibile  <br/> |Quando si prova ad aggiungere un connettore sia nel client che nella versione online, viene visualizzato il messaggio di errore: Si è verificato un errore imprevisto. Riprovare. Eseguire: Set-OrganizationConfig -ConnectorsEnabled=True   <br/> |Disabilitare con le impostazioni di Teams. Consultare il seguente articolo del supporto tecnico: https://answers.microsoft.com/en-us/msoffice/forum/msoffice_o365admin-mso_teams-mso_o365b/how-to-enable-or-disable-connectors-in-office-365/33d4b2c1-00eb-420a-ad83-01a2b42ad098    <br/> |21/06/2017  <br/> |

## <a name="apps"></a>App

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Gli utenti di Chrome versione 80 non possono accedere ad alcune app nella piattaforma di Teams.<br/>|Dopo che gli utenti hanno immesso correttamente le credenziali nella pagina di accesso di un'app, inizia un ciclo continuo in cui l'utente non viene riconosciuto e viene reindirizzato alla pagina di accesso dell'app. <br/>|Indicare agli utenti di usare il client desktop di Teams. |15/11/19<br/> |

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|[L'accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) potrebbe non funzionare se si usa la scheda "Sito Web" nell'app desktop<br/> |Se un sito Web, come un portale Intranet, include criteri di accesso condizionale (ad esempio le restrizioni relative agli indirizzi IP o al browser) potrebbe non essere visualizzato come scheda all'interno dell'app desktop di Teams. <br/> |Usare Teams in un browser invece dell'app desktop.  <br/> |01/07/2018  <br/> |

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Opzioni Connettori mancanti per alcuni team  <br/> |Quando si fa clic con il pulsante destro del mouse su un canale, l'opzione Connettori non è presente per nessun membro del team.  <br/> |Il creatore del team deve avere una cassetta postale online, in caso contrario, non sarà disponibile l'opzione Connettori. Si tratta di un comportamento previsto.  <br/> |26/06/2017  <br/> |

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|L'app "Attività" rimane visibile quando è disabilitata  <br/> |Quando l'app "Attività" è disabilitata nell'interfaccia di amministrazione, rimane visibile nel client di Teams per gli utenti con licenza EDU. Se la si seleziona quando è disabilitata, verrà visualizzato il seguente messaggio di errore: "Accidenti! Si è verificato un problema... "  <br/> |Non ci sono soluzioni alternative.  <br/> |29/12/2017  <br/> |

## <a name="audio-conferencing"></a>Audioconferenza

|**Problema**|**Comportamento/sintomi**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|I chiamanti PSTN con lo stesso numero "Da" sono indicati come medesimo utente nell'elenco dei partecipanti alle riunioni.  <br/> |Quando più chiamanti PSTN partecipano a una riunione e i loro ID chiamanti sono identificati come singolo numero, verranno visualizzati come un singolo chiamante nell'elenco dei partecipanti alle riunioni.  <br/> |Non ci sono soluzioni alternative.  <br/> |25/09/2017  <br/> |
|Il pannello Info riunione a volte non viene visualizzato.  <br/> |Il pannello Info riunione può non essere visualizzato nel client Teams quando gli utenti eseguono una ricerca per numero di telefono bridge conferenze o ID conferenze.  <br/> |Consultare i dettagli della riunione o il calendario di Outlook per vedere il numero di telefono bridge conferenza o l'ID conferenza.  <br/> |25/9/2017  <br/> |
|Gli inviti alle riunioni per il componente aggiuntivo Outlook mostrano caratteri senza significato per le coordinate PSTN per le localizzazioni diverse da US.  <br/> |Quando si programmano riunioni private con il componente aggiuntivo Outlook per Microsoft Teams in computer con localizzazione non US, le coordinate PSTN possono contenere caratteri senza significato.  <br/> |Non ci sono soluzioni alternative.  <br/> |25/9/2017  <br/> |
|L'accesso verso l'esterno richiede 5 cifre o più.  <br/> |Gli utenti che cercano di effettuare una chiamata verso l'esterno da una riunione devono digitare 5 o più cifre anche se è disponibile una regola di normalizzazione del piano di chiamata per normalizzare la composizione breve a E.164.  <br/> |Effettuare la chiamata con il numero DID o locale completo invece del numero interno.  <br/> |25/9/2017  <br/> |
|Il controllo per le chiamate esterne a volte non viene visualizzato.  <br/> |Il controllo per le chiamate esterne può non essere visibile nel pannello Info riunione.  <br/> |Non ci sono soluzioni alternative.  <br/> |25/09/2017  <br/> |
|Gli ID conferenza statici non sono supportati per le riunioni Microsoft Teams.  <br/> |Se l'amministratore sostituisce l'impostazione standard di ID conferenza dinamico con l'impostazione ID conferenza statico, questo non ha effetto per le riunioni di Microsoft Teams. Consulta [Uso degli ID audioconferenza dinamici nella tua organizzazione](/skypeforbusiness/audio-conferencing-in-office-365/using-audio-conferencing-dynamic-ids-in-your-organization.md).  <br/> |Non ci sono soluzioni alternative.  <br/> |25/9/2017  <br/> |
|Le coordinate riunione PSTN non sono disponibili per Skype for Business per gli utenti locali  <br/> |Se l'utente di Skype for Business è locale, assegnato con Skype for Business online, licenze di Audioconferenza e Teams, tutte le riunioni pianificate con Teams non includeranno le coordinate riunione PSTN. <br/> |Non ci sono soluzioni alternative.  <br/> |1/2/2018  <br/> |
|Informazioni sull'interoperabilità video nel cloud in Riunione immediata  <br/> |Se si crea un'istanza di Riunione immediata per una riunione in Microsoft Teams con una licenza IVC esistente, le informazioni sulla IVC non verranno popolate. <br/> |Si consiglia di pianificare la riunione per popolare tali informazioni.  <br/> |11/06/2019  <br/> |

## <a name="authentication"></a>Autenticazione

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Quando si prova ad accedere a Teams da Internet Explorer o Microsoft Edge, il programma si arresta in modo continuo o anomalo e non effettua l’accesso.   <br/> | L'organizzazione usa siti attendibili di Internet Explorer e l'applicazione basata sul Web di Teams non effettua correttamente l’accesso perché tali siti attendibili non sono consentiti per Teams. <br/>|Apportare le seguenti modifiche alle impostazioni di IE o dal pannello di controllo, con diritti di amministratore o con Oggetto Criteri di gruppo:<br/><ol><li>In **Opzioni Internet** &gt; **Privacy** &gt; **Impostazioni avanzate**, accettare i cookie di terze parti e dei siti Web visualizzati, quindi selezionare la casella **Accetta sempre i cookie della sessione**.</li><li>Fare clic su **Opzioni Internet** &gt; **Sicurezza** &gt; **Siti attendibili** &gt; **Siti**e aggiungere i seguenti indirizzi Web:<ul><li>https://login.microsoftonline.com</li><li>https://\*.teams.microsoft.com</li></ul></li></ol><br/><b>Nota</b>: convalidare e consentire sempre tutti gli URL attendibili per Teams e i requisiti del seguente documento sugli [intervalli degli indirizzi IP e URL di Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).   <br/> |01/11/2017  <br/> |

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Microsoft Teams accederà sempre all'account computer di dominio.   <br/> |Se un utente dispone di due account di Teams diversi ed è dotato di un computer con opzione di accesso al dominio abilitata, Teams userà il profilo di dominio presente sul computer per l'accesso automatico dell'utente all’applicazione. Per passare all’altro account di Teams, l'utente deve disconnettersi manualmente dall'app e immettere le credenziali di accesso del secondo account. Se l'utente si disconnette dall’app e riavvia il computer, Teams effettuerà l'accesso automatico usando il profilo di dominio. <br/> | Non ci sono soluzioni alternative. <br/> |02/08/2017  <br/> |

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Errore di autenticazione moderna - Autenticazione Forms non abilitata  <br/> |Se si verifica un errore iniziale con l'autenticazione a più fattori, usare l'app Web per effettuare l'autenticazione.  <br/> Per ulteriori informazioni, vedere [Supporto del parametro prompt=login di Active Directory Federation Services](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-prompt-login).  <br/> |Controllare questa impostazione: `Set -MsolDomainFederationSettings -DomainName yourdomainhere -PreferredAuthenticationProtocol WsFed -SupportsMfa $False -PromptLoginBehavior Disabled`.  <br/> |19/06/2017  <br/> |

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Pianificazione della build con Single Sign-on (SSO) <br/> |La funzionalità di SSO non si applica a Planner. Sarà necessario eseguire di nuovo l'accesso la prima volta che si usa Planner su ciascun client.  <br/> |Non ci sono soluzioni alternative. Sono in corso ulteriori miglioramenti riguardanti l'autenticazione.  <br/> |28/02/2017  <br/> |

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Impossibile salvare l'immagine del profilo  <br/> |Gli utenti non possono salvare l'immagine del profilo quando la cassetta postale di Exchange è ospitata (disponibile) in locale su Exchange 2016 CU2 o versione precedente.  <br/> |Non ci sono soluzioni alternative.  <br/> |28/02/2017  <br/> |

## <a name="browser"></a>Browser

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Artefatti verdi nel rendering video di Chrome  <br/> |Nel corso di una chiamata o di una riunione vengono visualizzati artefatti verdi, durante la riproduzione di video o la condivisione dello schermo, in Chrome.  <br/> |Disabilitare l'impostazione di accelerazione hardware in Chrome.  <br/> |03/08/2017  <br/> |

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Supporto client Web Safari  <br/> | Teams è ora disponibile in anteprima su Safari 11.1+ su macOS. In modalità anteprima gli utenti possono incorrere in [problemi noti di Safari](https://go.microsoft.com/fwlink/?linkid=2062082) relativi alla Prevenzione intelligente del tracciamento del browser.  <br/> | Mentre il supporto del browser Safari è in modalità anteprima, passare a **Preferenze > Privacy**  e deselezionare l'impostazione per  **Impedire il rilevamento intersito**  . Quindi, chiudere il browser e tornare a teams.microsoft.com in Safari. <br/> |02/11/2016  <br/> |


## <a name="channels"></a>Canali

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Quando un utente lascia l’organizzazione, viene visualizzato in Microsoft Teams come "utente sconosciuto"<br/> |Quando un utente lascia l’organizzazione, viene visualizzato in Microsoft Teams come "utente sconosciuto". Inoltre, viene visualizzata la scheda Conversazione: "L'utente sconosciuto è stato aggiunto al team". <br/> |Non ci sono soluzioni alternative.  <br/> |12/09/2017  <br/> |

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Gli utenti non possono ricreare il nome di un canale preesistente  <br/> |Dopo aver creato il nome di un canale, anche se quest’ultimo è stato eliminato, non è possibile ricrearlo. Il sistema conserva tali dati per gli scenari di protezione delle informazioni.  <br/> |Non ci sono soluzioni alternative.  <br/> |13/03/2017  <br/> |

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|La ridenominazione di un canale in Microsoft Teams non comporta la modifica del nome della corrispondente cartella in SharePoint Online  <br/> |Se un canale viene rinominato in Microsoft Teams, la cartella della raccolta documenti di SharePoint Online corrispondente al team non riflette tale modifica. Il nome corretto della cartella di SharePoint Online viene visualizzato nella parte superiore della scheda File del canale rinominato.  <br/> |Non ci sono soluzioni alternative.  <br/> |13/03/2017  <br/> |

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|L'anteprima dell'URL potrebbe non essere visualizzata per tutti gli URL  <br/> |Alcuni URL potrebbero non mostrare un'anteprima.  Ciò dipende dall'URL originale, le cui funzionalità consentono di visualizzare un'anteprima. <br/> |Non ci sono soluzioni alternative. <br/> |01/09/2018 <br/> |

## <a name="chat"></a>Chat

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Le menzioni @ per messaggi eliminati inviano una notifica con un collegamento al canale  <br/> |Esiste una limitazione di notifica nota quando si viene menzionati in un messaggio successivamente eliminato; la notifica nel feed passerà al canale ma non sarà associata a un messaggio specifico. <br/> | Si tratta di un comportamento previsto da progettazione <br/> | 28/03/2017  <br/>|


## <a name="client"></a>Client

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Impossibile avviare Teams per Surface Hub da Microsoft Store |Microsoft Teams per Surface Hub non viene avviato, quando si fa clic su **Avvia** in Microsoft Store. | L'avvio dell'app Teams per Surface Hub dall'elenco di Microsoft Store non è supportato da Windows in Surface Hub. <br> <br/> Riavviare Surface Hub dopo aver installato Teams. | 27/02/2018 |

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Teams non si aggiorna automaticamente   <br/> | Se Microsoft Teams viene installato in programmi che usano script di installazione anziché nel percorso predefinito, il client non esegue l'aggiornamento automatico quando le nuove versioni sono disponibili.    <br/> | Si tratta di un comportamento previsto da progettazione. Assicurarsi di installare l'applicazione nel percorso predefinito: `user\Appdata`.  <br/> | 07/09/2017  <br/> |

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Il collegamento simbolico o il mapping di un'unità su C:\users causa l’avvio dell'app con schermo bianco  <br/> | Se Microsoft Teams viene installato in programmi che usano script di installazione anziché nel percorso predefinito, il client non esegue l'aggiornamento automatico quando le nuove versioni sono disponibili.   <br/> | Si tratta di un comportamento previsto da progettazione. Assicurarsi di installare l'applicazione nel percorso predefinito: `user\Appdata`. Se il mapping deve essere presente, usare la versione Web di Microsoft Teams.  <br/> | 07/09/2017  <br/> |

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Il collegamento simbolico o il mapping di un'unità su c:\users causa l’avvio dell'app con schermo bianco  <br/> |Quando il percorso predefinito di `C:\users\<user>\appData` viene modificato spostando la cartella `C:\users` o usando il collegamento simbolico, l'app viene avviata con una schermata bianca.   <br/> |Non ci sono soluzioni alternative note. Se il mapping deve essere presente, usare la versione Web di Microsoft Teams.   <br/> |13/03/2017  <br/> |

## <a name="environment"></a>Ambiente

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Le cassette postali di gruppo non sono abilitate per scopi di archiviazione (memoria aggiuntiva)  <br/> |Nel Centro sicurezza e conformità di Office 365, gli amministratori globali non possono abilitare l'archiviazione nelle cassette postali di gruppo. È possibile abilitare l’archiviazione solo nelle cassette postali degli utenti.  <br/> |Se la capacità della cassetta postale di gruppo ha quasi raggiunto il limite massimo, contattare il supporto tecnico di Microsoft Office per estenderne le dimensioni.  <br/> |01/02/2017  <br/> |

## <a name="guest-access"></a>Accesso Guest

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|I clienti EU e APAC ricevono un messaggio di errore quando aggiungono un utente Guest da un altro tenant    <br/> | I clienti in EU e APAC sperimentano un ritardo di replica tra Microsoft Teams e Azure Active Directory. Se un utente di un tenant UE o APAC tenta di aggiungere un utente Guest da qualsiasi altro tenant, riceve il messaggio di errore in cui viene chiesto di riprovare a effettuare l’aggiunta.   <br/> |Fare di nuovo clic sul pulsante Riprova per effettuare l'aggiunta dell'utente Guest.  <br/> |08/11/2017  <br/> |

## <a name="linux"></a>Linux

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Avvio automatico su Linux non funzionante. <br/> |L'avvio automatico dell’applicazione Teams non funziona su Linux. <br/> | <br/> |05/12/2019  <br/>|

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Schermo bianco durante la riattivazione dalla modalità di sospensione. <br/> |Quando il computer viene riattivato dalla modalità di sospensione, è possibile che si verifichi una modifica della rete (in particolare, in caso di connessione del computer a una VPN prima che sia impostata la modalità sospensione) e può volerci del tempo prima che venga ripristinata la connessione. La combinazione di questi elementi può comportare lo schermo bianco in Teams. <br/> |Sarà utile il riavvio del client Teams.  <br/> |05/12/2019  <br/>|

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Cursore mancante durante la condivisione dello schermo. <br/> |Durante la condivisione dello schermo, l'altro utente connesso non vede il cursore della persona che condivide lo schermo. <br/> | <br/> |05/12/2019  <br/>|

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Problema nell’esecuzione in parallelo a VMWare Workstation. <br/> |L'applicazione Teams presenta problemi durante l'esecuzione in parallelo a VMWare Workstation.
 <br/> | <br/> |05/12/2019  <br/>|

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Le notifiche di KDE creano una nuova barra delle applicazioni.<br/> |La notifica su KDE crea una nuova finestra nella barra delle applicazioni. <br/> | <br/> |05/12/2019  <br/>|

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|I gestori dei pacchetti non visualizzano l’elenco di modifiche. <br/> |La gestione pacchetti non mostra l’elenco delle modifiche. <br/> | <br/> |05/12/19  <br/>|

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Impossibile avviare client Teams in modalità offline. <br/> |Non è possibile avviare Teams offline nel client Linux. <br/> | <br/> |05/12/2019  <br/>|

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Impostazioni del dispositivo durante una riunione. <br/> |Quando si partecipa a una riunione e si modificano le impostazioni del dispositivo, l'indicatore del microfono non registra nulla. <br/> | <br/> |05/12/2019  <br/>|

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Impossibile chiudere l'applicazione Teams mediante la tastiera. <br/> |Impossibile chiudere l'applicazione Teams usando la combinazione predefinita `$mod + shift + q` o facendo clic sul pulsante Chiudi nell'app. <br/> | <br/> |05/12/2019  <br/>|

## <a name="meetings"></a>Riunioni

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Gli utenti non possono accedere alle riunioni o ai connettori pur avendo le cassette postali di Exchange Online. <br/> |Il cliente blocca attivamente i servizi Web Exchange (EWS) dai servizi all’interno di Exchange Online, ma c’è bisogno che Microsoft Teams sia conforme ai criteri di EWS. <br/> |Per rendere conforme Microsoft Teams, è necessario aggiungere le seguenti stringhe agente utente per Microsoft Teams all'interno di EWSAllowList: `SkypeSpaces/*` e `MicrosoftNinja/*`, includendo gli asterischi. È possibile usare il comando seguente: `Set-organizationconfig -EwsAllowList @{Add="MicrosoftNinja/*","SkypeSpaces/*"}`<br/> Per altre informazioni: https://docs.microsoft.com/powershell/module/exchange/organization/Set-OrganizationConfig?view=exchange-ps <br/> |30/05/2017  <br/>|

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Skype for Business necessario per alcune riunioni  <br/> |Il calendario degli appuntamenti viene visualizzato comodamente in Microsoft Teams. Per partecipare a una riunione, fare clic sul pulsante **Partecipa**. <br/> Stiamo sviluppando nuove soluzioni a riguardo, tuttavia se la riunione è stata pianificata con Skype for Business e si fa clic su**Partecipa**, Microsoft Teams avvierà il client di Skype for Business per completare l'accesso alla riunione. Le riunioni pianificate in Microsoft Teams verranno avviate direttamente all'interno dell’applicazione.  <br/> In futuro, semplificheremo questa procedura.  <br/> |Fare clic su **Partecipa**. In base all'URL incluso nella descrizione della riunione, Microsoft Teams valuterà in modo intelligente se Skype for Business sia necessario affinché un determinato utente possa partecipare a una riunione.  <br/> |13/03/2017  <br/> |


|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Limite massimo di partecipanti alle riunioni  <br/> |Ogni riunione di Microsoft Teams può avere un massimo di 250 partecipanti.  <br/> |Creare eventi live in Teams che possono ospitare 10000 utenti.  <br/> |13/03/2017  <br/> |

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Funzionalità Riunioni non disponibile  <br/> |La funzionalità Riunioni non è disponibile quando la cassetta postale di Exchange è ospitata (disponibile) in locale su una versione di Exchange 2016 precedente alla CU3.  <br/> |Eseguire l'aggiornamento a Exchange 2016 CU3 o versione successiva per la distribuzione in locale.  <br/> |28/02/2017  <br/> |

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Audio mancante durante la condivisione di contenuti multimediali in riunioni broadcast  <br/> |Durante la condivisione di un contenuto multimediale in una riunione broadcast, l'audio del contenuto condiviso (collegamento YouTube o file video salvato) non può essere udito dai partecipanti.  <br/> |Nessuno dei partecipanti riesce ad ascoltare l’audio in quanto si tratta di un comportamento previsto da progettazione.  Teams attualmente non supporta l'audio dalla condivisione dei contenuti  <br/> |09/10/2018  <br/> |

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Impossibile avviare la riunione come organizzatore da Outlook in quanto si potrebbe rimanere bloccati nella sala di attesa virtuale  <br/> |Questo problema può verificarsi quando il client di Outlook è connesso a un account diverso da quello del client di Teams. <br/> |Quando si partecipa alla riunione, assicurarsi che il client di Outlook e il client di Teams vengano registrati nello stesso account in cui è stata pianificata la riunione.  <br/> |05/11/2018  <br/> |

## <a name="mobile"></a>Dispositivi mobili

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Impossibile visualizzare i canali aggiunti automaticamente ai Preferiti  <br/> |Alcuni membri non sono in grado di visualizzare i canali aggiunti automaticamente ai preferiti sull'app per dispositivi mobili.  <br/> |I membri devono eseguire prima l'accesso all’app Web o desktop per visualizzare i canali aggiunti automaticamente ai preferiti sull'app per dispositivi mobili.  <br/> |30/04/2018  <br/>|

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Gli utenti potrebbero non essere in grado di cambiare account nei dispositivi mobili gestiti da Intune  <br/> |Gli utenti potrebbero non essere in grado di cambiare account nei dispositivi mobili gestiti da Intune.  <br/> |Non ci sono soluzioni alternative.  <br/> |20/09/2017  <br/>|

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Problemi verificabili quando si usa iOS 13 Beta  <br/> |1. le notifiche di Teams non vengono inviate.  Il problema riguarda anche le chat, le menzioni e le chiamate.  2. L'anteprima dei file non funziona con la versione build beta.  <br/> |Al momento non ci sono soluzioni alternative disponibili.  Stiamo collaborando con gli sviluppatori Apple per trovare soluzioni a questi problemi.  <br/> | 25/06/2019  <br/>|


## <a name="people"></a>Persone

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Foto del profilo utente  <br/> | Attualmente Teams non dispone di un meccanismo per impedire agli utenti di modificare le foto. Il team di BTS si è riunito con il team di sviluppo, che ha presentato le seguenti considerazioni: funzionalità 108874: Criteri IT per disabilitare il caricamento delle foto del profilo   <br/> | I clienti interessati a una funzionalità per impedire il caricamento delle foto del profilo in Teams, possono aggiungere il proprio voto e caso aziendale ai commenti qui di seguito: https://microsoftteams.uservoice.com/forums/555103-public/suggestions/18600505-disable-user-ability-to-change-profile-photos <br/> |01/03/2017 <br/> |



## <a name="phone-system"></a>Sistema telefonico

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Reparto configurato non correttamente come account di risorsa <br/> | Gli account di risorsa locali, associati a un operatore automatico o alla coda delle chiamate, che siano stati creati prima di gennaio 2019, potrebbero non avere il parametro Reparto impostato correttamente. Questo scenario potrebbe causare un errore di assegnazione dei numeri di telefono. Stiamo approntando una correzione per risolvere il problema. <br/><br/> Gli account di risorsa configurati usando New-CsHybridApplicationEndpoint con Skype for Business Server potrebbero non avere il parametro Reparto impostato correttamente, rendendo impossibile la creazione dell'account di risorsa nell'interfaccia di amministrazione di Teams. In questo caso, è necessario configurare il nome del reparto in Active Directory in locale prima di eseguire la sincronizzazione online.|Per ovviare a questo problema, è possibile eseguire il seguente Cmdlet per impostare il parametro Reparto. Eseguire: Set-MsolUser -ObjectId <Resource Account Object ID> -Department "Microsoft Communication Application Instance" <br/> Consultare anche l’[Aggiornamento del servizio Coda delle chiamate e Operatore automatico](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521). |08/05/2019 <br/> |


|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Ritardo nella sincronizzazione degli account di risorsa|È impossibile assegnare un numero di telefono all'account di risorsa o viene visualizzato l'errore "La seguente istanza dell'applicazione non è presente in BVD".|Attendere 24 ore per permettere la sincronizzazione. Se sono già passate 24 ore, rimuovere l'assegnazione del numero di telefono, eliminare l'account di risorsa e crearne uno nuovo con un nome diverso.|18/05/2019|

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Impossibile assegnare un numero di servizio a pagamento dall'interfaccia di amministrazione di Teams|Quando si prova a assegnare un numero di servizio a pagamento nell'interfaccia di amministrazione di Teams, viene visualizzato l'errore "È necessaria la licenza del Sistema telefonico".|Usare invece i cmdlet di PowerShell per assegnare un numero di servizio a pagamento.|18/05/2019|


|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Account di risorsa danneggiato|L'account di risorsa non funziona|La rimozione o la sostituzione della licenza di un account di risorsa oppure la creazione di un nuovo account di risorsa con lo stesso URI SIP di una persona precedentemente eliminata comporterà il danneggiamento dell’account di risorsa.|18/05/2019|


|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Numero di telefono bloccato|Numero di telefono bloccato: l’eliminazione dell’account di risorsa prima della rimozione del corrispettivo numero di telefono comporta il blocco del numero di telefono.|Contattare il supporto Microsoft per sbloccare il numero di telefono.|18/05/2019|

## <a name="presence"></a>Icone di presenza
|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Le icone di presenza non vengono visualizzate in Outlook e in altre applicazioni di Office dopo aver spostato un utente in modalità **Solo Teams**. <br/> |Se si disinstalla il client di Skype for Business dopo aver spostato un utente in modalità **Solo Teams**, l’icona di presenza smetterà di funzionare in Outlook e in altre app di Office. L’icona di presenza funziona bene in Teams.  <br/> |Per visualizzare l’icona di presenza in Outlook e in altre app di Office, è necessario installare Skype for Business, anche se Team viene eseguito in modalità **Solo Teams**. Microsoft è a conoscenza del problema e sta lavorando per risolverlo.  <br/> |09/2019  <br/> |



## <a name="provisioning"></a>Provisioning

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Errato utente SharePoint creato per il sito SharePoint di Microsoft Teams  <br/> |Il creatore SharePoint per un gruppo Microsoft Teams risulta essere l’amministratore SharePoint e non l'utente corretto.  <br/> Durante il controllo dalla console di amministrazione di SharePoint, il creatore della pagina della raccolta sito associata al gruppo di Office 365, creato distintamente dal team in Microsoft Teams, è l'amministratore SharePoint.  <br/> |Non ci sono soluzioni alternative.  <br/> |21/17/2019  <br/> |

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Gli utenti non possono creare un team  <br/> |È possibile che l'organizzazione abbia impostato dei criteri restrittivi in modo che gli utenti non possano creare team o gruppi di Office 365.  <br/> |Rivolgersi all'amministratore IT per comprendere i criteri dell’organizzazione per la creazione di gruppi e team.  <br/> |13/03/2017  <br/> |

## <a name="skype-for-business-to-teams-upgrade"></a>Aggiornamento da Skype for Business a Teams

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|

## <a name="tabs"></a>Schede

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Le schede Sito Web creano confusione nei clienti  <br/> |Le schede Sito Web non sono equivalenti a quelle del browser. Alcuni siti, in particolare quelli che richiedono l'autenticazione o che usano popup, non funzioneranno se vengono aggiunti come schede Sito Web.  <br/> |Stiamo lavorando per migliorare l'interfaccia utente in modo da renderla più chiara ai clienti.  <br/> |02/05/2018  <br/>|

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Le schede non funzionano perché è stato abilitato l'accesso condizionale <br/> |Alcune schede potrebbero non essere più caricate nel client desktop poiché l'accesso condizionale è stato abilitato sul tenant. Le schede vengono caricate quando si usa il client Web. Alcune schede che potrebbero essere interessate da questo problema sono: Elenco SharePoint, PowerApps, VSTS, Forms, PowerBI.  <br/> |Per visualizzare le schede interessate dal problema, è necessario usare Teams in Microsoft Edge, IE o Chrome con l'estensione account di Windows 10 installata. Alcune schede dipendono ancora dall'autenticazione Web, che non funziona nel client desktop quando la CA è abilitata. Stiamo collaborando con i nostri partner per abilitare questi scenari. Finora abbiamo abilitato Planner, OneNote e Stream. <br/> |05/04/2018  <br/>|

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|L'elenco delle aree di lavoro non è alfabetico  <br/> |Gli utenti che cambiano area di lavoro, quando aggiungono una scheda PowerBI troveranno un elenco non alfabetico di aree di lavoro da scorrere.  <br/> |Non ci sono soluzioni alternative.  <br/> |13/03/2017  <br/>|

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|La barra di scorrimento scompare quando si selezionano i report  <br/> |Gli utenti che aggiungono report PowerBI non possono scorrere un elenco più lungo di una schermata di report senza che la barra di scorrimento scompaia.  <br/> |Usare le frecce in su e in giù per scorrere l'elenco.  <br/> |13/03/2017  <br/>|

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Integrazione di Planner in Teams con Planner online <br/> |I contenitori di attività in Planner non vengono visualizzati online in Planner per il Web.  <br/> |Non ci sono soluzioni alternative. <br/> |28/02/2017  <br/>|


|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Integrazione di Planner in Teams con Planner online <br/> |I proprietari non riescono a creare un piano per un team creato da un gruppo di Office 365 esistente.  <br/> |Assegnare le autorizzazioni di membro al proprietario del gruppo. <br/> |14/1/20  <br/>|




|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Scheda OneNote Legacy  <br/> |Le schede OneNote Legacy create durante l'anteprima pubblica di Microsoft Teams non possono essere rinominate o eliminate.  <br/> |Non ci sono soluzioni alternative. <br/> |08/11/2017  <br/> |

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Funzione Cerca nella scheda Elenco di SharePoint  <br/> |Se si prova ad aprire un file dalla funzione Cerca della scheda Elenco di SharePoint, viene visualizzato il messaggio "Avrai bisogno di una nuova app per aprire questo file" e il file non viene aperto. <br/> |Aprire direttamente il file dall'elenco invece che della barra di ricerca. <br/> |11/02/2019  <br/> |

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Errore nel download di file <br/> |Se si prova a scaricare un file quando il relativo percorso contiene un apostrofo, viene generato un errore che indica il mancato download del file quando si usa il client desktop di Microsoft Teams. <br/> |Scaricare il file dal client Web o da SharePoint Online <br/> |10/05/2019  <br/> |

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Non è possibile caricare o scaricare file di OneNote <br/> |Il tentativo di caricare o scaricare un file o un blocco appunti di OneNote con Microsoft Teams non andrà a buon fine. <br/> |Scaricare o caricare il file direttamente in SharePoint Online <br/> |07/05/2019  <br/> |

## <a name="teams"></a>Teams

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|I messaggi della segreteria telefonica di Teams verranno recapitati con errore SPF se si tratta di una chiamata SIP, con l'attributo FROM senza il valore corretto in caso di chiamata PSTN a un utente, mentre se il cliente ha una regola per l’analisi dei messaggi vocali SPF avrà l'azione in cui decide l'ETR. <br/> | <br/> | La soluzione alternativa del 29/08/2019 prevede l’aggiunta di un'eccezione in ETR se il messaggio è di tipo vocale.


|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Il caricamento delle foto in Teams non è bloccato in OWA/Outlook come richiesto dai criteri   <br/> | Teams consente agli utenti di caricare foto direttamente in Office 365, nonostante le impostazioni dei criteri in vigore impediscano il caricamento delle foto per OWA.   <br/> |<br/>  |16/10/2017  <br/> |

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|L'elenco dei team pubblici non mostra tutti i team  <br/> |L'elenco dei team pubblici si basa su Microsoft Graph.  <br/> |Se un determinato team non viene visualizzato, provare a cercarlo nella casella di ricerca in alto a destra. Inoltre, i proprietari del team devono comunicare ai colleghi il nome del team, perché molti team potrebbero essere visualizzati nei risultati della ricerca. <br/> | 21/07/2017  <br/>|

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|I nomi dei team che contengono caratteri speciali possono generare errori per la creazione di riunioni  <br/> |L’utente riceverà il messaggio **Si è verificato un errore** in rosso, quando prova a creare una riunione per un team contenente caratteri speciali nel nome.   <br/> |Rinominare o ricreare il team con un nome che non contenga una "/".  <br/> |13/07/2017  <br/> |

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Limite massimo di 5000 membri del team  <br/> |Ogni team Microsoft può avere un massimo di 5000 membri per ciascun team.  <br/> |Non ci sono soluzioni alternative.  <br/> |06/02/2019  <br/> |

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|L'eliminazione di un team causerà anche la cancellazione del gruppo ad esso associato  <br/> |Gli utenti potrebbero non comprendere che il gruppo di Office 365 sottostante viene cancellato quando il team viene eliminato. Inoltre, se viene eliminato il gruppo di Office 365 sottostante, verrà cancellato anche il team.  <br/> |Altre lingue in Microsoft Teams forniscono queste informazioni all'utente. Queste informazioni non sono presenti nell'interfaccia dei Gruppi di Office 365. Il supporto tecnico può recuperare un gruppo o un team eliminato.  <br/> |13/03/2017  <br/> |

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|App desktop Teams con schermo bianco  <br/> | <br/> |Provare a eliminare o reinstallare i driver di grafica sul computer oppure avviare Teams da una riga di comando con il contrassegno "disable-gpu".<ul><li>Per Windows: aprire il prompt dei comandi e immettere quanto segue: `cd %localappdata%\microsoft\teams\current run Teams.exe --disable-gpu`</li><li>Per Mac: avviare l’applicazione Terminale e immettere quanto segue: `cd \Applications folder Microsoft\ Teams.app/Contents/MacOS/Teams --disable-gpu`</li></ul> <br/> |<br/> |

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Mancata ricezione dell’email di benvenuto quando l’utente viene aggiunto dall’amministratore  <br/> |Quando si aggiunge un membro a un team usando PowerShell o l'interfaccia di amministrazione di Teams, il nuovo membro non riceve l’email di benvenuto da Microsoft Teams.  <br/> |L’aggiunta di un membro direttamente dall'interfaccia utente di Teams genererà l’invio di un messaggio di posta elettronica. Attualmente, non è disponibile alcuna soluzione alternativa a livello amministrativo.  <br/> |12/02/2019  <br/> |

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|Problema di interoperabilità tra Symantec DLP e Teams <br/> |Le istanze di DLP Endpoint Agent possono interferire con l’esecuzione di Teams e conseguentemente generare un errore di avvio o di uscita.  <br/> |Escludere dalle istanze di DLP Endpoint Agent (o includere nell'elenco elementi consentiti) Teams.exe, come descritto nel seguente <a href="https://support.symantec.com/us/en/article.TECH220322.html">articolo del supporto tecnico di Symantec</a>. <br/> |15/07/2019  <br/> |

|**Titolo del problema**|**Comportamento/sintomo**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|La crittografia dell può impedire l’avvio di Teams <br/> |La crittografia dell (in precedenza Crittografia per la protezione dei dati dell) può danneggiare l'installazione di Teams durante il processo di aggiornamento, causando un errore permanente durante l’avvio dell'applicazione. <br/> |Escludere la cartella Teams in %LocalAppData%\Microsoft\Teams dai criteri di crittografia. <br/> |21/11/19  <br/> |
