---
title: Chiamare i report di diagnostica (per utente) in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9da13470-001e-415f-b8c5-29b1f3b531ba
description: 'Riepilogo: informazioni sui report di diagnostica delle chiamate per utente usati in Skype for Business Server.'
ms.openlocfilehash: c2ef55243680cbb8bc088c2b056b298428b70b50
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992071"
---
# <a name="call-diagnostic-reports-per-user-in-skype-for-business-server"></a>Chiamare i report di diagnostica (per utente) in Skype for Business Server
  
I report di diagnostica delle chiamate contengono informazioni per utente sulle sessioni peer-to-peer e conferenze non riuscite. In questo momento esiste un solo report, il **report attività utente**.

Il report attività utente fornisce un elenco dettagliato delle sessioni peer-to-peer e di conferenza svolte dagli utenti in un determinato periodo di tempo. Diversamente da molti dei report di monitoraggio, il report attività utente lega ogni chiamata a singoli utenti. Ad esempio, le sessioni peer-to-peer specificano gli URI SIP della persona che ha avviato la chiamata (l'utente da) e la persona che veniva chiamata (l'utente). Se si espandono le informazioni per una conferenza, viene visualizzato un elenco di tutti i partecipanti alla conferenza e il ruolo che hanno tenuto per la conferenza.

Il report attività utente viene talvolta indicato come report "Help desk". Questo perché il report viene spesso usato dal personale dell'helpdesk per recuperare le informazioni sulla sessione per un utente specifico. Puoi filtrare le chiamate effettuate o effettuate da un singolo utente semplicemente digitando l'URI SIP dell'utente nella casella prefisso URI utente.

In questo caso, il report attività utente restituirà informazioni per tutti gli utenti il cui URI SIP inizia con la stringa specificata. Ad esempio, se si digita **Ken** nella casella URI, il report attività utente individuerà **Ken**. Myer@litwareinc.com. Verranno tuttavia individuati anche gli utenti seguenti:

- **davide** azi@litwareinc.com

- **davide** Burg@litwareinc.com

- **Ken**. Sanchez@litwareinc.com

- **Davide** Nedy@litwareinc.com

Per fare in modo che vengano restituite le informazioni solo per Ken, digitare l'URI completo (Ken.Myer@litwareinc.com) nella casella di ricerca o almeno il tipo di URI di Ken per distinguerlo in modo univoco dagli altri utenti dell'organizzazione. Ad esempio:

Ken.my

## <a name="to-access-the-user-activity-report"></a>Per accedere al report attività utente

Il report attività utente si accede dalla Home page dei report di monitoraggio. È anche possibile accedere al report attività utente facendo clic sulla metrica URI utente nel [report inventario IP telefono in Skype for Business Server](ip-phone-inventory-report.md). Dall'interno del report attività utente fare clic sull'URI conferenza (per una conferenza) per il report Dettagli conferenza. Analogamente, se si fa clic sulla metrica di dettaglio per una chiamata peer-to-peer si passa al [report Dettagli sessione peer-to-peer in Skype for Business Server](peer-to-peer-session-detail-report.md).

## <a name="making-the-best-use-of-the-user-activity-report"></a>Sfruttare al meglio il report attività utente

Anche se nel report attività utente sono presenti numerose informazioni utili, è possibile che le informazioni a volte siano difficili da individuare. Ad esempio, tutte le attività utente che si svolgono nell'organizzazione durante un periodo specificato sono incluse nel report attività utente; Questo significa che, sepolto, nel report sono disponibili informazioni su quali utenti hanno effettivamente usato Skype for Business Server in qualche modo.

> [!NOTE]
> Tecnicamente, è possibile che alcune attività dell'utente non vengano registrate: mentre Skype for Business Server si sforza di conservare le informazioni su tutte le telefonate, è possibile che sia stata eseguita una chiamata senza che le informazioni relative alla chiamata vengano scritte nel database. Skype for Business Server è progettato per dare un aspetto estremamente accurato ma non necessariamente perfetto su come viene usato Skype for Business Server. (Il fatto che non sia garantito che il 100% di tutte le chiamate sia registrato spiega perché il monitoraggio di Skype for Business Server non deve essere usato come sistema di fatturazione). In secondo luogo, un report di monitoraggio può solo visualizzare, al massimo, i record di 1.000. A seconda della quantità di attività utente in uso e in base al periodo di tempo in cui si sta lavorando, significa che la query potrebbe non restituire tutti i dati effettivamente archiviati nel database. 

- Quali utenti hanno effettivamente usato il sistema durante questo periodo di tempo?

- Quali utenti sono stati i più attivi durante questo periodo di tempo?

- Gli utenti che effettuano la maggior parte delle chiamate telefoniche sono anche gli utenti che partecipano alle sessioni di messaggistica istantanea più?

Se è necessario rispondere a domande di questo tipo, è possibile esportare i dati recuperati dai report di monitoraggio in un foglio di calcolo di Excel. Puoi quindi usare il foglio di calcolo e/o un file con valori delimitati da virgole per analizzare i dati in modo che il report attività utente. Si supponga ad esempio di aver esportato i dati del report in Excel e quindi in un file con valori delimitati da virgole. A questo punto è possibile importare i dati da. File CSV in Windows PowerShell usando un comando simile al seguente:

```PowerShell
$x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"
```

Dopo aver importato i dati, è possibile usare semplici comandi di Windows PowerShell per rispondere alle domande. Ad esempio, questo comando restituisce un elenco di utenti univoci che hanno servito come "da utente" in almeno una sessione:

```PowerShell
$x | Group-Object "From user" | Select Name | Sort-Object Name
```

In altre parole:

<pre>
Name
----
David.Ahs@litwareinc.com
Gilead.Amosnino@litwareinc.com
Henrik.Jensen@litwareinc.com
Ken.Myer@litwareinc.com
Pilar.Ackerman@litwareinc.com
</pre>

Questo comando elenca gli utenti univoci (in base al numero totale di sessioni a cui hanno partecipato:

```PowerShell
$x | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending
```

Che restituisce dati simili a questi:

<pre>
Count    Name
-----    ----
  523    Ken.Myer@litwareinc.com
   63    David.Ahs@litwareinc.com
   29    Pilar.Ackerman@litwareinc.com
   17    Gilead.Amosnino@litwareinc.com
   10    Henrik.Jensen@litwareinc.com
</pre>

Questo comando limita le sessioni segnalate a quelle che includevano l'audio come modalità:

```PowerShell
$x | Where-Object {$_.Modalities -match "audio"} | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending
```

Se si tiene il mouse su un ID di diagnostica visualizzato nel report, verrà visualizzata una descrizione comando che descrive l'ID.

## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Ad esempio, il report attività utente consente di filtrare i dati restituiti in base a elementi come il tipo di attività (ovvero sessioni peer-to-peer o sessioni di conferenza) o l'indirizzo SIP dell'utente (che consente di visualizzare le attività di un utente). È anche possibile scegliere la modalità di raggruppamento dei dati. In questo caso, gli usi vengono raggruppati per ora, giorno, settimana o mese.

Nella tabella seguente sono elencati i filtri che è possibile usare con il report attività utente.

**Filtri di report attività utente**


| **Nome**   | **Descrizione**  |
|:-----------|:--------|
| **Da** <br/>             | Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:  <br/> 7/17/12015 1:00 PM  <br/> Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/17/12015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/13/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/>                                                      |
| **A** <br/>               | Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:  <br/> 7/17/12015 1:00 PM  <br/> Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/17/12015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/13/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/>                                                             |
| **Tipo di attività** <br/>    | Tipo di attività. Selezionare una delle opzioni seguenti: <br/>  Tutti <br/>  Peer-to-peer <br/>  Conferenza <br/>      |
| **Modalità** <br/>         | La modalità disponibile varia in base al tipo di attività seleziona. Se il tipo di attività è peer-to-peer, è possibile selezionare la messaggistica istantanea. Trasferimento file; Condivisione di applicazioni; Segreteria telefonica o video come modalità.  <br/> Se il tipo di attività è conferenza, è possibile selezionare conferenza telefonica di messaggistica istantanea; Conferenza Web; Condivisione di applicazioni; Conferenza vocale/video; o conferenza telefonica.  <br/>         |
| **Categoria sessione** <br/> | Indica se l'attività in questione è riuscita o meno. Selezionare una delle opzioni seguenti: <br/>  Tutti <br/>  Successo <br/>  Errore previsto <br/>  Errore imprevisto <br/>  Un "errore previsto" è un errore che dovrebbe verificarsi; ad esempio, se un utente ha impostato il proprio stato su non disturbare, si prevede che qualsiasi chiamata non venga eseguita correttamente. Un "errore imprevisto" è un errore che si verifica in quello che sembrerebbe essere un sistema altrimenti integro. Ad esempio, una chiamata non deve essere terminata se il chiamante viene posizionato in attesa. Se questo si verifica, verrebbe contrassegnato come errore imprevisto. <br/> |
| **Prefisso URI utente** <br/>  | Indirizzo SIP per l'utente. Per visualizzare solo i record per l'utente Ken si deve immettere l'indirizzo SIP di Ken. Ad esempio:  <br/> sip:kenmyer@litwareinc.com  <br/>

## <a name="metrics-for-peer-to-peer-sessions"></a>Metriche per le sessioni peer-to-peer

Nella tabella seguente sono elencate le informazioni fornite nel report attività utente per le sessioni peer-to-peer, ovvero le sessioni che coinvolgono solo due partecipanti.

**Metriche per le sessioni peer-to-peer**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Dettaglio** <br/> |No  <br/> |Quando si fa clic su questo elemento, il report Mostra il report Dettagli sessione peer-to-peer per la sessione selezionata.  <br/> |
|**Dall'utente** <br/> |Sì  <br/> |Indirizzo SIP dell'utente che ha avviato la sessione peer-to-peer.  <br/> |
|**All'utente** <br/> |Sì  <br/> |Indirizzo SIP dell'utente che ha partecipato alla sessione peer-to-peer.  <br/> |
|**Modalità** <br/> |Sì  <br/> |Tipo di comunicazione usato nella sessione. Ad esempio, messaggistica istantanea, audio o trasferimento di file.  <br/> |
|**Invitare il tempo** <br/> |Sì  <br/> |Data e ora in cui è stato inviato l'invito iniziale a partecipare alla sessione peer-to-peer.  <br/> |
|**Tempo di risposta** <br/> |Sì  <br/> |Data e ora in cui l'utente "a" ha accettato l'invito alla sessione.  <br/> |
|**Ora di fine** <br/> |Sì  <br/> |Data e ora terminata la sessione peer-to-peer.  <br/> |
|**ID diagnostica** <br/> |Sì  <br/> |Identificatore univoco (in forma di intestazione MS-Diagnostics) allegato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione di errori. Le intestazioni di diagnostica sono facoltative (è possibile avere sessioni SIP che non includono queste intestazioni) e gli ID di diagnostica vengono riportati solo per le sessioni con problemi di qualche tipo.  <br/> |

## <a name="metrics-for-conferencing-sessions"></a>Metriche per le sessioni di conferenza

Nella tabella seguente sono elencate le informazioni fornite nel report attività utente per le sessioni di conferenza, ovvero le sessioni che coinvolgono tre o più partecipanti.

**Metriche per le sessioni di conferenza**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**URI conferenza** <br/> |Sì  <br/> |Identificatore di conferenza univoco. Quando si fa clic su questo elemento, il report Mostra il report Dettagli conferenza per la sessione selezionata. Quando si espande questo elemento, il report Mostra le informazioni sui partecipanti alla conferenza. Per informazioni dettagliate, vedere la sezione "metriche per partecipanti alla conferenza" più avanti in questo argomento.  <br/> |
|**Organizzatore** <br/> |Sì  <br/> |Indirizzo SIP dell'utente che ha organizzato la conferenza.  <br/> |
|**Pool** <br/> |Sì  <br/> |Nome del server perimetrale (se presente) usato nella conferenza.  <br/> |
|**Ora di inizio** <br/> |Sì  <br/> |Data e ora di inizio della conferenza.  <br/> |
|**Ora di fine** <br/> |Sì  <br/> |Data e ora di fine della conferenza.  <br/> |

## <a name="metrics-for-conference-participants"></a>Metriche per i partecipanti alla conferenza

La tabella seguente elenca le informazioni fornite nel report attività utente per ogni partecipante di una conferenza.

**Metriche per i partecipanti alla conferenza**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Ruolo** <br/> |No  <br/> |Ruolo conferenza, ad esempio relatore, per l'utente.  <br/> |
|**Partecipante** <br/> |No  <br/> |Indirizzo SIP dell'utente.  <br/> |
|**Connettività** <br/> |No  <br/> |Tipo di connessione di rete. Ad esempio "da Internal" per la connessione interna o "da PSTN" per gli utenti con accesso esterno.  <br/> |
|**Tempo di partecipazione** <br/> |No  <br/> |Data e ora in cui l'utente ha partecipato alla conferenza.  <br/> |
|**Ora di uscita** <br/> |No  <br/> |Data e ora in cui l'utente ha lasciato la conferenza.  <br/> |
|**ID diagnostica** <br/> |No  <br/> |Identificatore univoco (in forma di intestazione MS-Diagnostics) allegato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione di errori. Le intestazioni di diagnostica sono facoltative (è possibile avere sessioni SIP che non includono queste intestazioni) e gli ID di diagnostica vengono riportati solo per le sessioni con problemi di qualche tipo.  <br/> |

