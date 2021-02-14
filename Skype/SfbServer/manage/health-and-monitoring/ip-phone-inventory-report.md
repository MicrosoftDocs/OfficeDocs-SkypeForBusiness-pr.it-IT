---
title: Rapporto inventario telefoni IP in Skype for Business Server
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
ms.assetid: aa7d6b31-cb09-4e68-b020-aa5dd0081c20
description: 'Riepilogo: informazioni sul Rapporto inventario telefoni IP in Skype for Business Server.'
ms.openlocfilehash: 513b4ac54cf337a13cd95523fa3de750ce5f8c17
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823456"
---
# <a name="ip-phone-inventory-report-in-skype-for-business-server"></a>Rapporto inventario telefoni IP in Skype for Business Server
 
**Riepilogo:** Informazioni sul Rapporto inventario telefoni IP in Skype for Business Server.
  
Il Rapporto inventario telefoni IP riporta informazioni sui telefoni IP attualmente in uso nell'organizzazione. Il Rapporto inventario IP fornisce un elenco dettagliato dei telefoni IP effettivamente utilizzati durante il periodo di riferimento specificato. Tra le altre cose, questo report consente agli amministratori di sapere se ci sono telefoni vecchi e obsoleti ancora in uso che devono essere sostituiti; può anche avvisare gli amministratori del fatto che ci sono telefoni costosi nell'organizzazione che vengono usati raramente. Questo tipo di informazioni può essere di valore inestimabile quando arriva il momento di acquistare nuovi telefoni o di ridistribuire i telefoni esistenti. Ad esempio, a un utente che usa raramente il suo costoso telefono potrebbe essere richiesto di scambiare telefoni con un utente che usa il proprio telefono molto più frequentemente.
  
Si noti che questo report presenta alcune limitazioni quando si tratta di un report di inventario vero e proprio. Per prima cosa, il Rapporto telefoni IP elenca semplicemente tutti i telefoni che hanno effettuato l'accesso a Skype for Business Server durante il periodo di tempo specificato, ordinati in base all'ora dell'ultimo accesso. Se un telefono non ha avuto accesso durante il periodo di tempo specificato, non verrà elencato nel rapporto inventario. Sono inclusi i telefoni connessi prima dell'inizio del periodo di tempo e che sono ancora connessi durante l'intervallo di tempo specificato. Si supponga, ad esempio, di voler esaminare tutto l'inventario telefonico di luglio 2015. Si supponga, inoltre, che diversi telefoni si sono connessi a Skype for Business Server il 30 giugno 2015 e sono ancora connessi a partire dal 1° luglio. Questi telefoni non verranno visualizzati nel report inventario del 1° luglio.
  
È anche importante notare che il report di inventario potrebbe includere telefoni che l'organizzazione non usa più. Si supponga, ad esempio, che alcuni telefoni Fabrikam si sono connessi al sistema il 1° luglio 2015. 5 giorni dopo, l'organizzazione si è liberata di tutti i telefoni Fabrikam e li ha sostituiti con un modello Contoso più recente. I telefoni Fabrikam verranno comunque visualizzati nel report "inventario" semplicemente perché hanno eseguito l'accesso al sistema durante il mese di luglio.
  
Inoltre, il Rapporto inventario telefoni IP non riporta i totali riepilogati per i diversi tipi di telefoni. Si supponga, ad esempio, di avere 105 telefoni Polycom CX600. Il report non dirà che si dispone di 105 di questi telefoni; verranno invece semplicemente visualizzati 105 voci separate per Polycom Cx600. L'unico modo per sapere che sono presenti 105 voci per Polycom Cx600 è contare ognuna di queste voci manualmente.
  
> [!TIP]
> In caso contrario, esportare i dati e utilizzare Microsoft Excel o Windows PowerShell eseguire il conteggio per conto dell'utente. 
  
## <a name="accessing-the-ip-phone-inventory-report"></a>Accesso al Rapporto inventario telefoni IP

È possibile accedere al Rapporto inventario telefoni IP dalla home page dei rapporti di monitoraggio. Se fai clic sulla metrica URI utente, puoi accedere al Rapporto attività utente per tale utente. Se si fa clic sulla metrica Ultima attività per una chiamata peer-to-peer, verrà visualizzato il Rapporto dettagli sessione peer-to-peer. Se si fa clic sulla stessa metrica per una conferenza, verrà visualizzato il Rapporto dettagli conferenza.
  
## <a name="making-the-best-use-of-the-ip-phone-inventory-report"></a>Utilizzo ottimale del Rapporto inventario telefoni IP

Se si è interessati solo alle informazioni sull'utilizzo di un particolare tipo di telefono (ad esempio, "Con quale frequenza gli utenti usano un telefono Polycom CX600?"), è possibile ottenere queste informazioni direttamente dal Rapporto inventario telefoni IP filtrando per quel particolare tipo di telefono. Tuttavia, se si desiderano informazioni di riepilogo per tutti i telefoni (quante persone usano un Polycom CX600, quanti usano un LG-Nortel IP8540 e così via), sarà necessario esportare i dati e usare un'altra applicazione (ad esempio Windows PowerShell) per eseguire questo tipo di analisi. Si supponga, ad esempio, di esportare i dati in un file con valori delimitati da virgole (C:\Data\IP_Phone_Inventory_Report.csv). In tal caso, è possibile utilizzare questi due comandi per fornire dati di riepilogo per tutti i telefoni:
  
```PowerShell
$phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
$phones |Group-Object Manufacturer, "Hardware version" | Select-Object Count, Name | Sort-Object Count -Descending
```

Il comando restituisce dati analoghi a questi:
  
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

Analogamente, questi due comandi indicano quali telefoni hanno effettuato l'accesso al sistema ma non sono mai stati effettivamente utilizzati per effettuare una chiamata (il valore della metrica Ultima attività è vuoto, a indicare che non sono state apportate ultime attività):
  
```PowerShell
$phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
$phones | Where-Object {$_."Last activity" -eq ""}
```

In questo modo vengono restituiti dati simili ai seguenti per ogni telefono che non è stato utilizzato:
  
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

Un altro modo interessante per usare il Rapporto inventario telefoni IP è questo: se si ha l'indirizzo MAC di un telefono IP, è possibile trovare l'utente che lo ha usato per ultimo semplicemente immettendo tale indirizzo nella casella di testo dell'indirizzo MAC. Il rapporto inventario telefoni IP riporta, tra le altre cose, l'indirizzo SIP dell'utente che ha effettuato l'ultimo accesso con quel telefono. In alternativa, è possibile immettere un indirizzo SIP utente (nella casella Prefisso URI utente) per individuare tutti i telefoni utilizzati da tale utente.
  
## <a name="filters"></a>Filtri

I filtri consentono di ottenere un set di dati più specifico o di visualizzare in modo diverso i dati restituiti. Ad esempio, IP Phone Inventory consente di visualizzare solo i telefoni prodotti da una società specifica o anche una versione specifica di tali telefoni. È inoltre possibile scegliere la modalità di raggruppamento dei dati. In questo caso, le registrazioni sono raggruppate per ora, giorno, settimana o mese.
  
Nella tabella seguente sono elencati i filtri che è possibile utilizzare con il Rapporto inventario telefoni IP.
  
**Filtri rapporto inventario telefoni IP**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**From** <br/> |Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:  <br/> 07/07/2015 13.00  <br/> Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**To** <br/> |Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:  <br/> 07/07/2015 13.00  <br/> Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**Produttore** <br/> |Nome della società che ha prodotto il telefono IP. I valori per questo filtro vengono popolati automaticamente in base ai telefoni IP attualmente presenti nel database.  <br/> |
|**Versione hardware** <br/> |Numero di versione del telefono IP; utilizzando i filtri produttore e versione hardware è possibile identificare in modo univoco un particolare tipo di telefono. I valori per questo filtro vengono popolati automaticamente in base ai telefoni IP attualmente presenti nel database.  <br/> |
|**Agente utente** <br/> |Identificatore del software utilizzato dal telefono IP. I valori per questo filtro vengono popolati automaticamente in base ai telefoni IP attualmente presenti nel database.  <br/> |
|**Indirizzo MAC** <br/> |Identificatore univoco dell'interfaccia di rete nel telefono IP. L'indirizzo MAC (Media Access Control) viene in genere assegnato al momento della produzione del telefono e viene collegato all'hardware del dispositivo.  <br/> Per cercare i record relativi a un indirizzo MAC specifico, immettere semplicemente tale indirizzo. Ad esempio:  <br/> 00-08-5D-16-16-48  <br/> È necessario immettere l'indirizzo completo. Un indirizzo parziale (ad esempio 00-08-5D) non restituisce dati.  <br/> |
|**Ultima attività prima dei giorni** <br/> | Selezionare uno dei seguenti valori: <br/>  [All] <br/>  10   <br/>  20 <br/>  30 <br/> |
|**Ora ultima disconnessione prima dei giorni** <br/> | Selezionare uno dei seguenti valori: <br/>  [All] <br/>  10   <br/>  20 <br/>  30 <br/> |
|**Prefisso URI utente** <br/> |Indirizzo SIP dell'utente che ha utilizzato il telefono IP.  <br/> |
   
## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni fornite nel Rapporto inventario telefoni IP.
  
**Metriche del rapporto inventario telefoni IP**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Produttore** <br/> |Sì  <br/> |Nome della società che ha prodotto il telefono IP.  <br/> |
|**Versione hardware** <br/> |Sì  <br/> |Numero di versione del telefono IP.  <br/> |
|**Indirizzo MAC** <br/> |Sì  <br/> |Identificatore univoco dell'interfaccia di rete nel telefono IP. L'indirizzo MAC viene in genere assegnato al momento della produzione del telefono e viene collegato all'hardware del dispositivo.  <br/> |
|**URI utente** <br/> |Sì  <br/> |Indirizzo SIP dell'utente che ha utilizzato il telefono IP.  <br/> |
|**Agente utente** <br/> |Sì  <br/> |Identificatore del software utilizzato dal telefono IP.  <br/> |
|**Ora ultimo accesso** <br/> |Sì  <br/> |Data e ora dell'ultimo accesso del telefono IP a Skype for Business Server.  <br/> |
|**Ora ultima disconnessione** <br/> |Sì  <br/> |Data e ora dell'ultimo accesso del telefono IP da Skype for Business Server.  <br/> |
|**Ultima attività** <br/> |Sì  <br/> |Data e ora dell'ultimo utilizzo del telefono IP.  <br/> |
   

