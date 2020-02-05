---
title: USA config. XML per eseguire attività di installazione nei client Skype for business
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: "Riepilogo: come usare il file config. XML per specificare altre istruzioni per l'installazione."
ms.openlocfilehash: a935e3623e99324eb24caef4e7e232d2311c5cfb
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768649"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a>USA config. XML per eseguire attività di installazione nei client Skype for business

**Riepilogo:** Come usare il file config. XML per specificare altre istruzioni per l'installazione.

Anche se lo strumento di personalizzazione di Office (OCT) è lo strumento principale per l'installazione di personalizzazione, gli amministratori possono usare il file config. XML per specificare altre istruzioni per l'installazione che non sono disponibili in ottobre. Le personalizzazioni seguenti possono essere eseguite solo usando il file config. XML:

- Specificare il percorso del punto di installazione della rete.

- Selezionare i prodotti da installare.

- Configurare la registrazione e la posizione del file di personalizzazione della configurazione e degli aggiornamenti software.

- Specificare le opzioni di installazione, ad esempio nome utente.

- Copiare l'origine di installazione locale (LIS) nel computer dell'utente senza installare Office.

- Aggiungere o rimuovere lingue dall'installazione.

Ti consigliamo di usare il file config. XML per configurare l'installazione silenziosa di Skype for business. 

Per impostazione predefinita, il file config. xml archiviato nella cartella principale del prodotto, ad esempio \ _Product_. WW) indirizza la configurazione per l'installazione di tale prodotto. Ad esempio, il file config. XML nella cartella seguente installa Skype for business:

- \\server\share\Skype15\Skype.WW \Config.xml

Gli elementi config. XML usati più comunemente per l'installazione di Skype for business sono elencati nella tabella seguente.

**Elementi config. XML**


| **Elemento**              | **Descrizione**                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configurazione  <br/>     | Elemento di primo livello (obbligatorio). Contiene l'attributo Product, ad esempio: Product = Lync (questo funzionerà per i client Skype for business)  <br/>                                                                                                                                                          |
| OptionState  <br/>       | Specifica il modo in cui vengono gestite le caratteristiche specifiche del prodotto durante l'installazione. Usare gli attributi seguenti per impedire l'installazione di servizi di integrazione applicativa, che includono componenti condivisi che interferiscono con Outlook: <br/>  ID = "LOBiMain" <br/>  Stato = "assente" <br/>  Children = "forza" <br/> |
| Visualizzare  <br/>           | Il livello di interfaccia utente visualizzato per l'installazione per l'utente. Gli attributi tipici includono i seguenti: <br/>  CompletionNotice = "Sì"                                                                                                                                                                                |
| Registrazione  <br/>           | Opzioni per il tipo di registrazione eseguito dall'installazione. Gli attributi tipici includono i seguenti: <br/>  Digitare = "disattivato"                                                                                                                                                                                       |
| Impostazione  <br/>           | Specifica i valori per le proprietà di Windows Installer. Gli attributi tipici includono i seguenti: <br/>  Setting ID = " *Name*" (il nome della proprietà di Windows Installer)  <br/>  Value = " *value*" (il valore da assegnare alla proprietà)  <br/>                                                             |
| DistributionPoint  <br/> | Percorso completo del punto di installazione di rete da cui eseguire l'installazione. Include l'attributo location: <br/>  Location = " *path*"  <br/>                                                                                                                                     |

L'esempio seguente mostra un file config. XML per una tipica installazione silenziosa del client Skype for business. 

```xml
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

Informazioni dettagliate sull'uso del file config. XML per eseguire attività di installazione e manutenzione di Office sono [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514)disponibili all'indirizzo.

## <a name="to-customize-the-configxml-file"></a>Per personalizzare il file config. XML

1. Aprire il file config. XML usando uno strumento di editor di testo, ad esempio Blocco note.

2. Individuare le righe che contengono gli elementi che si desidera modificare.

3. Modificare la voce dell'elemento con le opzioni Silent che si desidera utilizzare. Assicurarsi di rimuovere i delimitatori di commento, "\<!--" e "--\>". Ad esempio, usare la sintassi seguente:

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. Salvare il file config. XML.


