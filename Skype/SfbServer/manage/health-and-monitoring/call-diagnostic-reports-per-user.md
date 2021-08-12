---
title: Rapporti di diagnostica delle chiamate (per utente) in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9da13470-001e-415f-b8c5-29b1f3b531ba
description: 'Riepilogo: informazioni sui rapporti di diagnostica delle chiamate per utente usati in Skype for Business Server.'
ms.openlocfilehash: b04050b2d2efb94781d310983083c2c3b8e86c30965a3467cc5fcabfc2aa00fb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54280969"
---
# <a name="call-diagnostic-reports-per-user-in-skype-for-business-server"></a>Rapporti di diagnostica delle chiamate (per utente) in Skype for Business Server
  
I rapporti di diagnostica delle chiamate forniscono informazioni per utente sulle sessioni peer-to-peer e di conferenza non riuscite. Al momento esiste un solo report, il **Rapporto attività utente.**

Nel Rapporto attività utente viene fornito un elenco dettagliato delle sessioni peer-to-peer e di conferenza per ogni utente in riferimento a un periodo di tempo specifico. Diversamente da molti rapporti di monitoraggio, il Rapporto attività utente associa ogni chiamata al singolo utente. Ad esempio le sessioni peer-to-peer specificano gli URI SIP della persona che ha effettuato la chiamata (Da utente) e della persona che ha ricevuto la chiamata (A utente). Se si espandono le informazioni relative a una conferenza, è possibile visualizzare un elenco di tutti i partecipanti con l'indicazione del ruolo che hanno svolto nella conferenza.

Spesso si fa riferimento al Rapporto attività utente come al rapporto "help desk", in quanto il rapporto viene spesso utilizzato dal personale dell'help desk per recuperare informazioni sulla sessione per un utente specifico. È possibile applicare un filtro in base alle chiamate effettuate o ricevute da un singolo utente semplicemente digitando l'URI SIP dell'utente nella casella Prefisso URI utente.

In questo caso, il Rapporto attività utente restituirà informazioni per qualsiasi utente il cui URI SIP inizia con la stringa specificata. Ad esempio, se si digita **ken** nella casella URI, il Rapporto attività utente individua **Ken.** Myer@litwareinc.com. Tuttavia, individua anche questi utenti:

- **ken** azi@litwareinc.com

- **ken** burg@litwareinc.com

- **Ken**. Sanchez@litwareinc.com

- **Ken** nedy@litwareinc.com

Per assicurarsi che le informazioni solo per Ken Myer siano restituite, digita il suo URI completo (Ken.Myer@litwareinc.com) nella casella di ricerca o almeno un tipo di URI di Ken sufficiente per distinguerlo in modo univoco dagli altri utenti dell'organizzazione. Ad esempio:

Ken.my

## <a name="to-access-the-user-activity-report"></a>Per accedere al Rapporto attività utente

È possibile accedere al Report attività utente dalla home page dei report di monitoraggio. Puoi anche raggiungere il Rapporto attività utente facendo clic sulla metrica URI utente nel Report inventario Telefono [ip in Skype for Business Server](ip-phone-inventory-report.md). Dall'interno del Rapporto attività utente, facendo clic sull'URI conferenza (per una conferenza) si visualizza il Rapporto dettagli conferenza. Analogamente, facendo clic sulla metrica Dettagli per una chiamata peer-to-peer si visualizza il Rapporto dettagli sessione [peer-to-peer in Skype for Business Server](peer-to-peer-session-detail-report.md).

## <a name="making-the-best-use-of-the-user-activity-report"></a>Utilizzo ottimale del report attività utente

Anche se il Rapporto attività utente contiene molte informazioni, a volte può essere difficile individuarlo. Ad esempio, tutte le attività utente che si svolgono nell'organizzazione durante un periodo specificato sono incluse nel Rapporto attività utente. ciò significa che, nascosto, all'interno del report sono informazioni sugli utenti che hanno effettivamente usato Skype for Business Server in qualche modo.

> [!NOTE]
> Tecnicamente, è possibile che alcune attività degli utenti non vengano registrare: mentre Skype for Business Server cerca di mantenere le informazioni su tutte le chiamate telefoniche, è possibile che una chiamata possa essere stata effettuata senza che le informazioni sulla chiamata siano state scritte nel database. Skype for Business Server è progettato per offrire uno sguardo estremamente accurato, ma non necessariamente perfetto, al modo Skype for Business Server viene usato. Il fatto che non vi sia alcuna garanzia che il 100% di tutte le chiamate sia registrato spiega perché il monitoraggio Skype for Business Server non deve essere utilizzato come sistema di fatturazione. In secondo momento, un report di monitoraggio può visualizzare al massimo 1.000 record. Ciò significa che, a seconda della quantità di attività utente svolta e del periodo di tempo di riferimento, la query potrebbe non restituire tutti i dati effettivamente memorizzati nel database. 

- Quali utenti hanno effettivamente usato il sistema in questo periodo di tempo?

- Qual è stato l'utente più attivo in questo periodo di tempo?

- Gli utenti che effettuano il numero maggiore di chiamate telefoniche sono anche quelli che partecipano alla maggior parte di sessioni di messaggistica istantanea?

Per rispondere a domande come queste, è possibile esportare i dati recuperati dai rapporti di monitoraggio in un foglio di calcolo di Excel. Successivamente si può utilizzare questo foglio di calcolo e/o un file di valori separati da virgole per analizzare i dati in modo analogo al Rapporto attività utenti. Si supponga ad esempio di avere esportato i dati di rapporto in Excel, quindi in un file di valori separati da virgole. A questo punto, è possibile importare i dati dal file .CSV in Windows PowerShell utilizzando un comando simile al seguente:

```PowerShell
$x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"
```

Dopo aver importato i dati, puoi usare semplici comandi Windows PowerShell per rispondere alle tue domande. Il comando seguente, ad esempio, restituisce un elenco di utenti univoci che in almeno una sessione sono stati gli utenti di "Da utente":

```PowerShell
$x | Group-Object "From user" | Select Name | Sort-Object Name
```

In altri termini:

<pre>
Name
----
David.Ahs@litwareinc.com
Gilead.Amosnino@litwareinc.com
Henrik.Jensen@litwareinc.com
Ken.Myer@litwareinc.com
Pilar.Ackerman@litwareinc.com
</pre>

Questo comando elenca gli utenti univoci in base al numero totale di sessioni a cui hanno partecipato:

```PowerShell
$x | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending
```

Restituisce dati simili ai seguenti:

<pre>
Count    Name
-----    ----
  523    Ken.Myer@litwareinc.com
   63    David.Ahs@litwareinc.com
   29    Pilar.Ackerman@litwareinc.com
   17    Gilead.Amosnino@litwareinc.com
   10    Henrik.Jensen@litwareinc.com
</pre>

Questo comando limita le sessioni incluse nel rapporto a quelle che includevano l'audio come modalità:

```PowerShell
$x | Where-Object {$_.Modalities -match "audio"} | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending
```

Posizionando il mouse su un ID diagnostica mostrato nel rapporto, viene visualizzata una descrizione comando che descrive l'ID.

## <a name="filters"></a>Filtri

I filtri consentono di restituire un insieme di dati più circoscritto o di visualizzare in modi diversi i dati restituiti. Il Rapporto attività utente ad esempio consente di filtrare i dati restituiti in base a fattori come il tipo di attività, ovvero sessioni peer-to-peer o di conferenza, oppure in base all'indirizzo SIP dell'utente in modo da visualizzare le attività per un solo utente. È inoltre possibile scegliere come raggruppare i dati. In questo caso, gli utilizzi vengono raggruppati per ora, giorno, settimana o mese.

Nella tabella riportata di seguito vengono elencati i filtri che è possibile utilizzare con il Rapporto attività utente.

**Filtri per il Rapporto attività utente**


| **Nome**   | **Descrizione**  |
|:-----------|:--------|
| **From** <br/>             | Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:  <br/> 17/07/12015 13.00  <br/> Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/17/12015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/13/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/>                                                      |
| **To** <br/>               | Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:  <br/> 17/07/12015 13.00  <br/> Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/17/12015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/13/2015  <br/> Le settimane vengono calcolate sempre dal lunedì alla domenica.  <br/>                                                             |
| **Tipo di attività** <br/>    | Tipo di attività. Selezionare uno dei valori seguenti: <br/>  [All] <br/>  Peer-to-peer <br/>  Conferenza <br/>      |
| **Modalità** <br/>         | La modalità disponibile varia a seconda del tipo di attività selezionato. Se il tipo di attività è Peer-to-Peer, è possibile selezionare Messaggistica istantanea. Trasferimento file; Condivisione applicazioni; Voce; o Video come modalità.  <br/> Se il tipo di attività è Conferenza, è possibile selezionare Messaggistica istantanea Telefono conferenza; Conferenza Web; Condivisione applicazioni; Conferenza vocale/video; o Conferenza telefonica.  <br/>         |
| **Categoria sessione** <br/> | Indica l'esito dell'attività in questione. Selezionare uno dei valori seguenti: <br/>  [All] <br/>  Operazione completata <br/>  Errore previsto <br/>  Errore imprevisto <br/>  Per "errore previsto" si intende un errore che si prevede si verificherà. Se ad esempio un utente ha impostato il proprio stato su Non disturbare, è previsto che le chiamate effettuate per tale utente abbiano esito negativo. Per "errore imprevisto" si intende un errore che si verifica in un sistema considerato integro. Una chiamata ad esempio non dovrebbe interrompersi quando il chiamante viene messo in attesa. Se la chiamata si interrompe, l'evento verrà contrassegnato come errore imprevisto. <br/> |
| **Prefisso URI utente** <br/>  | Indirizzo SIP dell'utente. Per visualizzare solo i record relativi all'utente Ken Myer, è necessario immettere l'indirizzo SIP di Ken Myer, ad esempio:  <br/> sip:kenmyer@litwareinc.com  <br/>

## <a name="metrics-for-peer-to-peer-sessions"></a>Metrica per le sessioni peer-to-peer

Nella tabella riportata di seguito vengono elencate le informazioni fornite nel Rapporto attività utente per le sessioni peer-to-peer, ovvero le sessioni che coinvolgono solo due partecipanti.

**Metrica per le sessioni peer-to-peer**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Dettagli** <br/> |No  <br/> |Quando si fa clic su questo elemento, nel rapporto viene mostrato il Rapporto Dettagli sessione peer-to-peer per la sessione selezionata.  <br/> |
|**Da utente** <br/> |Sì  <br/> |Indirizzo SIP dell'utente che ha avviato la sessione peer-to-peer.  <br/> |
|**A utente** <br/> |Sì  <br/> |Indirizzo SIP dell'utente che ha partecipato alla sessione peer-to-peer.  <br/> |
|**Modalità** <br/> |Sì  <br/> |Tipo di comunicazione utilizzato nella sessione, ad esempio messaggistica istantanea, audio o trasferimento file.  <br/> |
|**Ora invito** <br/> |Sì  <br/> |Data e ora di invio dell'invito iniziale a partecipare alla sessione peer-to-peer.  <br/> |
|**Ora risposta** <br/> |Sì  <br/> |Data a ora in cui l'utente invitato ha accettato l'invito per la sessione.  <br/> |
|**Ora fine** <br/> |Sì  <br/> |Data e ora di fine della sessione peer-to-peer.  <br/> |
|**ID diagnostica** <br/> |Sì  <br/> |Identificatore univoco nel formato di un'intestazione ms-diagnostics associato a un messaggio SIP in cui spesso vengono fornite informazioni utili per la risoluzione dei problemi. Le intestazioni di diagnostica sono facoltative (è possibile che in alcune sessioni SIP non siano incluse queste intestazioni) e gli ID diagnostica sono spesso indicati solo per sessioni in cui si sono verificati problemi di un determinato tipo.  <br/> |

## <a name="metrics-for-conferencing-sessions"></a>Metrica per le sessioni di conferenza

Nella tabella riportata di seguito vengono elencate le informazioni fornite nel Rapporto attività utente per le sessioni di conferenza, ovvero le sessioni che coinvolgono tre o più partecipanti.

**Metrica per le sessioni di conferenza**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**URI conferenza** <br/> |Sì  <br/> |Identificatore di conferenza univoco. Quando si fa clic su questo elemento, nel rapporto viene mostrato il Rapporto Dettagli conferenza per la sessione selezionata. Quando si espande questo elemento, nel rapporto vengono mostrate le informazioni sui partecipanti della conferenza. Per informazioni, vedere la sezione "Metrica per i partecipanti di una conferenza" più avanti in questo argomento.  <br/> |
|**Organizzatore** <br/> |Sì  <br/> |Indirizzo SIP dell'utente che ha organizzato la conferenza.  <br/> |
|**Pool** <br/> |Sì  <br/> |Nome dell'eventuale server perimetrale utilizzato nella conferenza.  <br/> |
|**Ora inizio** <br/> |Sì  <br/> |Data e ora di inizio della conferenza.  <br/> |
|**Ora fine** <br/> |Sì  <br/> |Data e ora di fine della conferenza.  <br/> |

## <a name="metrics-for-conference-participants"></a>Metrica per i partecipanti di una conferenza

Nella tabella riportata di seguito vengono elencate le informazioni fornite nel Rapporto attività utente per ogni partecipante di una conferenza.

**Metrica per i partecipanti di una conferenza**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Ruolo** <br/> |No  <br/> |Ruolo dell'utente nella conferenza, ad esempio Relatore.  <br/> |
|**Partecipante** <br/> |No  <br/> |Indirizzo SIP dell'utente.  <br/> |
|**Connettività** <br/> |No  <br/> |Tipo di connessione di rete, ad esempio "Dall'interno" per una connessione interna o "Da PSTN" per gli utenti connessi tramite chiamata in ingresso.  <br/> |
|**Ora partecipazione** <br/> |No  <br/> |Data e ora in cui l'utente ha partecipato alla conferenza.  <br/> |
|**Ora uscita** <br/> |No  <br/> |Data e ora in cui l'utente è uscito dalla conferenza.  <br/> |
|**ID diagnostica** <br/> |No  <br/> |Identificatore univoco nel formato di un'intestazione ms-diagnostics associato a un messaggio SIP in cui spesso vengono fornite informazioni utili per la risoluzione dei problemi. Le intestazioni di diagnostica sono facoltative (è possibile che in alcune sessioni SIP non siano incluse queste intestazioni) e gli ID diagnostica sono spesso indicati solo per sessioni in cui si sono verificati problemi di un determinato tipo.  <br/> |

