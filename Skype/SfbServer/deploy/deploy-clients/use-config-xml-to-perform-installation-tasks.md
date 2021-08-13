---
title: Utilizzare Config.xml per eseguire attività di installazione in Skype for Business client
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: 'Riepilogo: come usare il file Config.xml per specificare istruzioni di installazione aggiuntive.'
ms.openlocfilehash: b7c04a9c08f6a5dd51c21a189ce3a07d81a589cf694e5020a75cf6f646bd1cef
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54332048"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a>Utilizzare Config.xml per eseguire attività di installazione in Skype for Business client

**Riepilogo:** Come usare il file Config.xml per specificare istruzioni di installazione aggiuntive.

Sebbene lo Strumento di personalizzazione di Office sia lo strumento principale per l'installazione della personalizzazione, gli amministratori possono utilizzare il file Config.xml per specificare istruzioni di installazione aggiuntive non disponibili nello Strumento di personalizzazione di Office. È possibile eseguire le personalizzazioni seguenti solo mediante il file Config.xml:

- Specificare il percorso del punto di installazione di rete.

- Selezionare i prodotti da installare.

- Configurare la registrazione e il percorso del file di personalizzazione dell'installazione e degli aggiornamenti software.

- Specificare le opzioni di installazione, ad esempio il nome utente.

- Copiare l'origine di installazione locale nel computer dell'utente senza installare Office.

- Aggiungere o rimuovere lingue dall'installazione.

È consigliabile utilizzare il file Config.xml per configurare l Skype for Business installazione invisibile all'utente. 

Per impostazione predefinita, Config.xml file archiviato nella cartella di base del prodotto (ad esempio, \ _product_. WW) indica al programma di installazione di installare il prodotto. Ad esempio, il file Config.xml nella cartella seguente viene installato Skype for Business:

- \\server\share\Skype15\Skype. WW \Config.xml

Gli Config.xml più comunemente utilizzati per l Skype for Business installazione sono elencati nella tabella seguente.

**Config.xml elementi**


| **Elemento**              | **Descrizione**                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configurazione  <br/>     | Elemento di primo livello (obbligatorio). Contiene l'attributo Product, ad esempio: Product=Lync (funziona per Skype for Business client)  <br/>                                                                                                                                                          |
| OptionState  <br/>       | Specifica come vengono gestite caratteristiche specifiche del prodotto durante l'installazione. Utilizzare gli attributi seguenti per impedire l'installazione di Servizi di integrazione applicativa, che include componenti condivisi che interferiscono con Outlook: <br/>  Id="LOBiMain" <br/>  State="Absent" <br/>  Children="Force" <br/> |
| Visualizza  <br/>           | Livello di interfaccia utente visualizzato all'utente dal programma di installazione. Di seguito sono riportati gli attributi tipici: <br/>  CompletionNotice="Yes"                                                                                                                                                                                |
| Registrazione  <br/>           | Opzioni per il tipo di registrazione eseguita dal programma di installazione. Di seguito sono riportati gli attributi tipici: <br/>  Type ="Off"                                                                                                                                                                                       |
| Impostazione  <br/>           | Specifica i valori per le Windows installer. Di seguito sono riportati gli attributi tipici: <br/>  Setting Id=" *name*" (il nome della Windows Installer)  <br/>  Value=" *value*" (valore da assegnare alla proprietà)  <br/>                                                             |
| DistributionPoint  <br/> | Percorso completo del punto di installazione di rete da cui deve essere eseguita l'installazione Include l'attributo Location: <br/>  Location=" *path*"  <br/>                                                                                                                                     |

Nell'esempio seguente viene illustrato un file Config.xml per un'installazione invisibile all'utente tipica del client Skype for Business client. 

```xml
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

Informazioni dettagliate sull'utilizzo del file Config.xml per eseguire Office attività di installazione e manutenzione sono disponibili all'indirizzo [https://go.microsoft.com/fwlink/p/?linkid=267514](/previous-versions/office/office-2013-resource-kit/cc179195(v=office.15)) .

## <a name="to-customize-the-configxml-file"></a>Per personalizzare il file Config.xml

1. Aprire il file Config.xml utilizzando uno strumento editor di testo, ad esempio Blocco note.

2. Individuare le righe che contengono gli elementi che si desidera modificare.

3. Modificare la voce di elemento con le opzioni invisibile all'utente che si desidera utilizzare. Assicurarsi di rimuovere i delimitatori di commento " \<!--" and "--\> ". Utilizzare ad esempio la sintassi seguente:

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. Salvare il file Config.xml.