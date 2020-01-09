---
title: Report sull'inventario dei telefoni IP in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7d6b31-cb09-4e68-b020-aa5dd0081c20
description: "Riepilogo: informazioni sul report sull'inventario dei telefoni IP in Skype for Business Server."
ms.openlocfilehash: 51d4a3a7cbd4bf856efa93ae04c25accc5415796
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992171"
---
# <a name="ip-phone-inventory-report-in-skype-for-business-server"></a>Report sull'inventario dei telefoni IP in Skype for Business Server
 
**Riepilogo:** Informazioni sul report sull'inventario dei telefoni IP in Skype for Business Server.
  
Il report inventario IP Phone riporta le informazioni sui telefoni IP attualmente in uso nell'organizzazione. Il report inventario IP include un elenco dettagliato dei telefoni IP effettivamente usati durante il periodo di riferimento specificato. Tra le altre cose, questo report consente agli amministratori di sapere se sono ancora in uso vecchi telefoni obsoleti che devono essere sostituiti. può anche avvisare gli amministratori del fatto che nell'organizzazione sono presenti telefoni costosi che raramente vengono usati. Questo tipo di informazioni può essere prezioso quando arriva il momento di acquistare nuovi telefoni o di ridistribuire i telefoni esistenti. Ad esempio, un utente che usa raramente il suo telefono costoso può essere invitato a scambiare telefoni con un utente che usa il suo telefono molto più spesso.
  
Si noti che il report presenta alcune limitazioni quando viene usato come report di inventario vero. Per prima cosa, il report IP Phone elenca semplicemente tutti i telefoni che hanno effettuato l'accesso a Skype for Business Server durante il periodo di tempo specificato, ordinati in base all'ora dell'ultimo accesso. Se un telefono non ha eseguito l'accesso durante il periodo di tempo specificato, non verrà elencato nel report inventario. Che include i telefoni che hanno effettuato l'accesso prima del periodo di tempo iniziato e che sono stati ancora connessi durante l'intervallo di tempo specificato. Supponiamo, ad esempio, di voler esaminare tutte le scorte telefoniche di luglio 2015. Supponiamo anche che diversi telefoni abbiano effettuato l'accesso a Skype for Business Server il 30 giugno 2015 ed abbiano ancora effettuato l'accesso a partire dal 1 ° luglio. I telefoni non verranno visualizzati nel report scorte per il 1 ° luglio.
  
È anche importante notare che il report inventario può includere i telefoni che l'organizzazione non usa più. Supponiamo ad esempio che un numero di telefoni Fabrikam sia connesso al sistema il 1 ° luglio 2015; 5 giorni dopo l'organizzazione si è sbarazzata di tutti i telefoni Fabrikam e li ha sostituiti con un modello contoso più recente. I telefoni Fabrikam verranno comunque visualizzati nel report "inventario" semplicemente perché hanno effettuato l'accesso al sistema durante il mese di luglio.
  
Inoltre, il report inventario IP Phone non riporta i totali di riepilogo per i diversi tipi di telefono. Supponiamo, ad esempio, di avere 105 telefoni CX600 Polycom. Il report non ti dirà che hai 105 di questi telefoni; verranno invece visualizzate semplicemente voci separate di 105 per la Cx600 Polycom. L'unico modo per sapere che ci sono 105 voci per il Polycom Cx600 consiste nel contare ognuna di queste voci manualmente.
  
> [!TIP]
> In alternativa, esportare i dati e usare Microsoft Excel o Windows PowerShell per eseguire il conteggio per l'utente. 
  
## <a name="accessing-the-ip-phone-inventory-report"></a>Accesso al report inventario IP Phone

Il report inventario IP Phone si accede dalla Home page dei report di monitoraggio. Se si fa clic sulla metrica URI utente, è possibile accedere al report attività utente per l'utente. Facendo clic sulla metrica Ultima attività per una chiamata peer-to-peer si accede al report Dettagli sessione peer-to-peer. Se si fa clic sulla stessa metrica per una conferenza, sarà possibile eseguire il report Dettagli conferenza.
  
## <a name="making-the-best-use-of-the-ip-phone-inventory-report"></a>Sfruttare al meglio il report inventario IP Phone

Se si è interessati solo alle informazioni sull'uso di un determinato tipo di telefono (ad esempio, "con quale frequenza Gli utenti usano un telefono CX600 Polycom?"), è possibile ottenere queste informazioni direttamente dal report inventario del telefono IP filtrando per quel particolare tipo di telefono. Tuttavia, se vuoi informazioni di riepilogo per tutti i telefoni (quante persone usano un Polycom CX600, quanti usano un IP8540 LG-Nortel e così via), dovrai esportare i dati e usare un'altra applicazione (ad esempio Windows PowerShell) per eseguire questo tipo di analisi. Si supponga ad esempio di esportare i dati in un file con valori delimitati da virgole (C:\Data\ IP_Phone_Inventory_Report. csv). In questo caso, puoi usare questi due comandi per specificare i dati di riepilogo per tutti i telefoni:
  
```PowerShell
$phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
$phones |Group-Object Manufacturer, "Hardware version" | Select-Object Count, Name | Sort-Object Count -Descending
```

Che restituirà dati simili a questi:
  
<pre>
Count    Name
-----    ----
  267    POLYCOM, CX700
  267    POLYCOM, CX600
  166    POLYCOM, C
   68    Microsoft, CPE
   64    LG-Nortel, IP8540
   59    Aastra, 6725ip
   37    LG-Nortel, IP
   22    POLYCOM, CX3000
   11    Microsoft, CPE_A
    9    POLYCOM, CX500
    7    Aastra, 6721ip
</pre>

Allo stesso modo, questi due comandi indicano i telefoni connessi al sistema, ma che non sono mai stati effettivamente usati per effettuare una chiamata (il valore della metrica Ultima attività è vuoto, che indica che non è stata eseguita alcuna Ultima attività):
  
```PowerShell
$phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
$phones | Where-Object {$_."Last activity" -eq ""}
```

Che restituisce dati simili a quelli per ogni telefono che non è stato usato:
  
<pre>
Manufacturer     : POLYCOM
Hardware version : CX600
MAC address      : 00-04-F2-00-01-76
User URI         : 422
User agent       : CPE/4.0.7423.1 OCPhone/4.0.7423.1 (Microsoft Lync 2010 (Beta) Phone Edition)
Last logon time  : 8/30/2010 4:44:48 PM
Last logoff time : 8/30/2010 5:59:07 PM
Last activity    :
</pre>

Un altro modo interessante per usare il report di inventario dei telefoni IP è il seguente: se si ha l'indirizzo MAC di un telefono IP, è possibile trovare l'ultimo utente che ha usato il telefono semplicemente inserendo l'indirizzo nella casella di testo indirizzo MAC. Il report inventario IP Phone riferirà (tra le altre cose) l'indirizzo SIP dell'utente che ha effettuato l'accesso con il telefono. In alternativa, è possibile immettere un indirizzo SIP utente (nella casella prefisso URI utente) per scoprire tutti i telefoni usati dall'utente.
  
## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Ad esempio, l'inventario del telefono IP consente di visualizzare solo i telefoni prodotti da una società specifica o anche una versione specifica di questi telefoni. È anche possibile scegliere la modalità di raggruppamento dei dati. In questo caso, le registrazioni vengono raggruppate per ora, giorno, settimana o mese.
  
Nella tabella seguente sono elencati i filtri che è possibile usare con il report inventario IP Phone.
  
**Filtri di report inventario IP Phone**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**Da** <br/> |Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
|**A** <br/> |Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
|**Produttore** <br/> |Nome della società che ha prodotto il telefono IP. I valori per questo filtro vengono popolati automaticamente in base ai telefoni IP attualmente presenti nel database.  <br/> |
|**Versione hardware** <br/> |Numero di versione del telefono IP; usando il produttore e i filtri della versione hardware puoi identificare in modo univoco un determinato tipo di telefono. I valori per questo filtro vengono popolati automaticamente in base ai telefoni IP attualmente presenti nel database.  <br/> |
|**Agente utente** <br/> |Identificatore per il software usato dal telefono IP. I valori per questo filtro vengono popolati automaticamente in base ai telefoni IP attualmente presenti nel database.  <br/> |
|**Indirizzo MAC** <br/> |Identificatore univoco per l'interfaccia di rete sul telefono IP. L'indirizzo MAC (Media Access Control) viene in genere assegnato nel momento in cui il telefono viene fabbricato e collegato all'hardware del dispositivo.  <br/> Per cercare i record relativi a un indirizzo MAC specifico, è sufficiente immettere l'indirizzo. Ad esempio:  <br/> 00-08-5D-16-16-48  <br/> È necessario immettere l'indirizzo completo. Un indirizzo parziale (ad esempio 00-08-5D) non restituisce dati.  <br/> |
|**Ultima attività prima del giorno** <br/> | Selezionare uno dei valori seguenti: <br/>  Tutti <br/>  10 <br/>  20 <br/>  30 <br/> |
|**Ultima ora di disconnessione prima del giorno** <br/> | Selezionare uno dei valori seguenti: <br/>  Tutti <br/>  10 <br/>  20 <br/>  30 <br/> |
|**Prefisso URI utente** <br/> |Indirizzo SIP dell'utente che ha usato il telefono IP.  <br/> |
   
## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni fornite nel report sull'inventario dei telefoni IP.
  
**Metriche del report inventario IP Phone**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Produttore** <br/> |Sì  <br/> |Nome della società che ha prodotto il telefono IP.  <br/> |
|**Versione hardware** <br/> |Sì  <br/> |Numero di versione del telefono IP.  <br/> |
|**Indirizzo MAC** <br/> |Sì  <br/> |Identificatore univoco per l'interfaccia di rete sul telefono IP. L'indirizzo MAC viene in genere assegnato nel momento in cui il telefono viene fabbricato e viene collegato all'hardware del dispositivo.  <br/> |
|**URI utente** <br/> |Sì  <br/> |Indirizzo SIP dell'utente che ha usato il telefono IP.  <br/> |
|**Agente utente** <br/> |Sì  <br/> |Identificatore per il software usato dal telefono IP.  <br/> |
|**Ora ultimo accesso** <br/> |Sì  <br/> |Data e ora dell'ultima volta che il telefono IP ha effettuato l'accesso a Skype for Business Server.  <br/> |
|**Ultima ora di disconnessione** <br/> |Sì  <br/> |Data e ora in cui il telefono IP ha eseguito l'ultimo disconnessione da Skype for Business Server.  <br/> |
|**Ultima attività** <br/> |Sì  <br/> |Data e ora dell'ultima volta che è stato usato il telefono IP.  <br/> |
   

