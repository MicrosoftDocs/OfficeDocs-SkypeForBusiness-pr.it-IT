---
title: Rapporto utilizzo Response Group in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3248b320-a552-400a-8485-6891af4eb0f3
description: "Riepilogo: informazioni sull'applicazione Response Group in Skype for Business Server."
ms.openlocfilehash: 6d065f8313a770ce05b10925c9c854cec7e256e5
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58623628"
---
# <a name="response-group-usage-report-in-skype-for-business-server"></a>Rapporto utilizzo Response Group in Skype for Business Server

**Riepilogo:** Informazioni sull'applicazione Response Group in Skype for Business Server.

L'applicazione Response Group consente a Skype for Business Server di rispondere e instradare le chiamate telefoniche in base al numero composto e, facoltativamente, alle risposte del chiamante a una serie di domande. In genere, le chiamate a Response Group non vengono instradate a una singola persona ma piuttosto a un team di persone definito gruppo di agenti. Ad esempio, se qualcuno chiama il numero di telefono dell'help desk, Skype for Business Server instradare automaticamente la chiamata al primo agente dell'help desk disponibile. In alternativa, Skype for Business Server può porre una serie di domande ("Premere 1 se si verificano problemi hardware. Premere 2 in caso di problemi software. Premere 3 se si verificano problemi di rete."), quindi instradare la chiamata all'agente dell'help desk più appropriato in base alla risposta a tali domande.

Il Rapporto di utilizzo dei Response Group fornisce una specifica dettagliata del numero di chiamate telefoniche ricevute da tutti i flussi di lavoro di Response Group e quindi suddivide tali chiamate in categorie più limitate, ad esempio Chiamate offerte, Chiamate con risposta e Chiamate interrotte.

Per lavorare con il Rapporto di utilizzo di Response Group è fondamentale comprendere la differenza tra i tipi di chiamate segnalate:

- **Chiamate ricevute**. Numero totale di chiamate ricevute da tutte le istanze dell'applicazione Response Group.

- **Chiamate riuscite**. Numero totale di chiamate prese dall'applicazione Response Group.

- **Chiamate offerte**. Numero totale di chiamate trasferite a un agente Response Group.

- **Chiamate con risposta**. Numero totale di chiamate che hanno effettivamente ricevuto una risposta da un agente Response Group.

- **Percentuale di chiamate interrotte**. Percentuale delle chiamate ricevute dall'applicazione Response Group ma che non hanno ricevuto risposta da un agente. Questo valore viene calcolato sottraendo le Chiamate con risposta dalle Chiamate ricevute e quindi dividendo tale valore per il numero di Chiamate ricevute. Se, ad esempio, sono state ricevute 10 chiamate di cui 7 con risposta, è necessario sottrarre 7 a 10. Il risultato sarà 3 chiamate senza risposta. Tale valore deve essere quindi diviso per 10, in modo da ottenere una percentuale di chiamate interrotte pari al 30%.

- **Chiamate trasferite**. Numero totale di chiamate a Response Group che sono state trasferite a causa di un timeout o di un overflow della coda.

Se osservando il Rapporto di utilizzo di Response Group non si ricorda la definizione di uno di questi tipi di chiamate, è sufficiente posizionare il mouse sull'etichetta del tipo di chiamata appropriata per visualizzare una descrizione comandi con una breve descrizione.

Il Rapporto di utilizzo di Response Group consente di applicare un filtro a un URI di un flusso di lavoro (l'indirizzo SIP associato a tale flusso di lavoro). Gli URI dei flussi di lavoro, tuttavia, non vengono visualizzati nel rapporto. Se si desidera sapere, ad esempio, quali flussi di lavoro stanno rispondendo al maggior numero di chiamate o quali flussi di lavoro stanno registrando il maggior numero di chiamate trasferite, fare clic sulla metrica appropriata per aprire il rapporto Elenco chiamate di Response Group relativo al tale periodo di tempo. Nel rapporto saranno elencati gli URI dei flussi di lavoro.

## <a name="accessing-the-response-group-usage-report"></a>Accesso al Rapporto di utilizzo di Response Group

L'accesso al Rapporto di utilizzo di Response Group può essere effettuato dalla home page di Relazioni monitoraggio. È possibile eseguire il drill-down al Rapporto elenco chiamate di [Response Group in Skype for Business Server](call-list-report.md) facendo clic su una delle metriche seguenti:

- Chiamate ricevute

- Chiamate riuscite

- Chiamate offerte

- Chiamate con risposta

- Chiamate trasferite

## <a name="making-the-best-use-of-the-response-group-usage-report"></a>Uso ottimale del Rapporto di utilizzo di Response Group

Uno degli usi più interessanti del Rapporto di utilizzo di Response Group potrebbe non essere immediatamente evidente, ovvero la capacità di recuperare informazioni sull'utilizzo per un singolo flusso di lavoro di Response Group.

> [!CAUTION]
> Un flusso di lavoro di Response Group è fondamentalmente un set di istruzioni che determina le Skype for Business Server quando un utente compone un determinato numero di telefono. A tale scopo, ogni flusso di lavoro è associato in modo univoco a un numero di telefono. Quando un utente chiama tale numero, il flusso di lavoro determina la modalità di gestione della chiamata. Ad esempio, il flusso di lavoro potrebbe causare l'instradamento della chiamata a una serie di domande IVR (Interactive Voice Response) che richiedono al chiamante di immettere informazioni aggiuntive ("Premere 1 per il supporto hardware. Premere 2 per il supporto software."). In alternativa, il flusso di lavoro potrebbe causare l'inserimento della chiamata in una coda e mettere in attesa il chiamante finché un agente non sarà disponibile per rispondere alla chiamata. La disponibilità degli agenti per la risposta alle chiamate dipende anche dal flusso di lavoro: i flussi di lavoro vengono usati per configurare sia l'orario di ufficio (i giorni della settimana e le ore del giorno in cui gli agenti sono disponibili per rispondere alle chiamate) che le festività (i giorni in cui non vi sono agenti disponibili per rispondere alle chiamate). Ogni volta che si compone un numero di telefono appartenente all'applicazione Response Group, si chiama essenzialmente un flusso di lavoro di Response Group. 

Sebbene gli URI dei flussi di lavoro non vengano visualizzati nel Rapporto di utilizzo di Response Group, è comunque possibile visualizzare le statistiche di utilizzo per un singolo flusso di lavoro, operazione che è spesso molto utile. Si supponga, ad esempio, di aver lanciato di recente una nuova campagna pubblicitaria e di essere curioso di sapere se gli utenti stanno chiamando per chiedere informazioni sul prodotto in questione. Se un flusso di lavoro di Response Group è stato associato al numero di telefono indicato per la campagna pubblicitaria, è possibile verificare facilmente se e quante persone stanno componendo tale numero.

È possibile adottare un approccio simile anche per misurare il numero di chiamate gestite dall'helpdesk interno o dal Servizio clienti.

Per esaminare le statistiche di utilizzo per un determinato flusso di lavoro, immettere l'URI del flusso di lavoro nella casella URI flusso di lavoro. Naturalmente, come si è fatto presente, gli URI del flusso di lavoro (l'indirizzo SIP associato a un flusso di lavoro) non vengono visualizzati nel report. Ciò significa che devi trovare un altro modo per determinare l'URI di un flusso di lavoro. Un modo per eseguire questa operazione è usare Windows PowerShell e Skype for Business Server Management Shell. Ad esempio, questo comando restituisce gli URI per tutti i flussi di lavoro di Response Group:

```PowerShell
Get-CsRgsWorkflow | Select-Object Name, PrimaryUri
```

I dati restituiti saranno simili ai seguenti:

<pre>
Name                            PrimaryUri
----                            ----------
Customer Support                sip:support@litwareinc.com
Help Desk                       sip:helpdesk@litwareinc.com
New Ad Campaign                 sip:newads@litwareinc.com
</pre>

Questo comando restituisce informazioni relative a un singolo flusso di lavoro, ovvero "New Ad Campaign":

```PowerShell
Get-CsRgsWorkflow -Name "New Ad Campaign" | Select-Object Name, PrimaryUri
```

## <a name="filters"></a>Filtri

I filtri consentono di restituire un insieme di dati più circoscritto o di visualizzare in modi diversi i dati restituiti. Il Rapporto di utilizzo di Response Group ad esempio consente di visualizzare i dati di tutti i flussi di lavoro di Response Group o di un singolo flusso di lavoro. È inoltre possibile scegliere come raggruppare i dati. In questo caso, gli utilizzi vengono raggruppati per ora, giorno, settimana o mese.

Nella tabella riportata di seguito vengono elencati i filtri che è possibile utilizzare con il Rapporto di utilizzo di Response Group.

**Filtri del Rapporto di utilizzo di Response Group**


| **Nome**               | **Descrizione**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **From** <br/>         | Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:  <br/> 07/07/2015 13.00  <br/> Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/>                                                                                                                              |
| **To** <br/>           | Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:  <br/> 07/07/2015 13.00  <br/> Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/>                                                                                                                                     |
| **Interval** <br/>     | Selezionare uno dei seguenti: <br/>  Orario (è possibile visualizzare un massimo di 25 ore) <br/>  Giornaliero (è possibile visualizzare un massimo di 31 giorni) <br/>  Settimanale (è possibile visualizzare un massimo di 12 settimane) <br/>  Mensile (è possibile visualizzare un massimo di 12 mesi) <br/>  Se le date di inizio e fine superano il numero massimo di valori consentiti per l'intervallo specificato, verrà visualizzato solo il numero massimo di valori a partire dalla data di inizio. Se ad esempio si seleziona l'intervallo giornaliero con data di inizio 7/07/2015 e data di fine 28/02/2015, verranno visualizzati i dati relativi ai giorni 07/08/2015 12.00 alle 07.00.00 12.00 (ovvero un totale di 31 giorni di dati). <br/> |
| **URI flusso di lavoro** <br/> | Consente di limitare i dati restituiti al flusso di lavoro di Response Group specificato. Per utilizzare questo filtro, immettere l'indirizzo SIP del flusso di lavoro, ad esempio:  <br/> sip:helpdesk@litwareinc.com  <br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |

## <a name="metrics"></a>Metriche

Nella tabella seguente vengono elencate le informazioni fornite nel Rapporto di utilizzo di Response Group.

**Metrica del Rapporto di utilizzo di Response Group**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Orario** <br/> **Giornaliero** <br/> **Settimanale** <br/> **Mensile** <br/> |No  <br/> |Indica l'intervallo di tempo selezionato. Ove applicabile, è possibile fare clic su un determinato intervallo di tempo per visualizzare informazioni dettagliate relative a tale intervallo. Ad esempio, se si utilizza l'intervallo Giornaliero e si fa clic su 7/07/07/2015, verrà visualizzata una suddivisione oraria dell'attività di registrazione degli utenti per tale data.  <br/> |
|**Chiamate ricevute** <br/> |No  <br/> |Numero totale di chiamate ricevute da tutte le istanze dell'applicazione Response Group. Quando si fa clic su questo elemento, viene visualizzato il Rapporto Elenco chiamate Response Group relativo all'intervallo di tempo selezionato.  <br/> |
|**Chiamate riuscite** <br/> |No  <br/> |Numero totale di chiamate che hanno ricevuto riposta dall'applicazione Response Group. Quando si fa clic su questo elemento, viene visualizzato il Rapporto Elenco chiamate Response Group relativo all'intervallo di tempo selezionato.  <br/> |
|**Chiamate offerte** <br/> |No  <br/> |Numero totale di chiamate trasferite a un agente di Response Group. Quando si fa clic su questo elemento, viene visualizzato il Rapporto Elenco chiamate Response Group relativo all'intervallo di tempo selezionato.  <br/> |
|**Chiamate con risposta** <br/> |No  <br/> |Numero totale di chiamate a cui effettivamente è stata fornita una risposta da un agente di Response Group. Quando si fa clic su questo elemento, viene visualizzato il Rapporto Elenco chiamate Response Group relativo all'intervallo di tempo selezionato.  <br/> |
|**Percentuale di chiamate interrotte** <br/> |No  <br/> |Numero totale di chiamate ricevute dall'applicazione Response Group ma alle quali non è stata mai fornita risposta da un agente. Questo valore viene calcolato sottraendo il valore di Chiamate con risposta dal valore di Chiamate ricevute e quindi dividendo tale valore per il numero di chiamate ricevute. Se ad esempio sono state ricevute 10 chiamate, di cui sette con risposta, sarà necessario sottrarre sette da 10, lasciando tre chiamate senza risposta. Tale valore verrà poi diviso per 10 e si otterrà una percentuale di chiamate interrotte pari al 30%.  <br/> |
|**Media minuti chiamata per agente** <br/> |No  <br/> |Quantità media di tempo dedicata da una gente di Response Group per chiamata.  <br/> |
|**Chiamate trasferite** <br/> |No  <br/> |Numero totale di chiamate di Response Group trasferite a causa del timeout o dell'overflow di una coda. Quando si fa clic su questo elemento, viene visualizzato il Rapporto Elenco chiamate Response Group relativo all'intervallo di tempo selezionato.  <br/> |


