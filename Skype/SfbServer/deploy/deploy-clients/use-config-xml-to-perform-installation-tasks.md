---
title: Usare Config.xml per eseguire attività di installazione nei client Skype for Business
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
description: 'Riepilogo: informazioni su come utilizzare il Config.xml per specificare istruzioni di installazione aggiuntive.'
ms.openlocfilehash: 1b8aeeb16e061e7816e475f01c9cd9a9146306ee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825186"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a>Usare Config.xml per eseguire attività di installazione nei client Skype for Business

**Riepilogo:** Come usare il file Config.xml per specificare istruzioni di installazione aggiuntive.

Sebbene lo Strumento di personalizzazione di Office sia lo strumento principale per l'installazione della personalizzazione, gli amministratori possono utilizzare il file Config.xml per specificare istruzioni di installazione aggiuntive non disponibili nello Strumento di personalizzazione di Office. È possibile eseguire le personalizzazioni seguenti solo mediante il file Config.xml:

- Specificare il percorso del punto di installazione di rete.

- Selezionare i prodotti da installare.

- Configurare la registrazione e il percorso del file di personalizzazione dell'installazione e degli aggiornamenti software.

- Specificare le opzioni di installazione, ad esempio il nome utente.

- Copiare l'origine di installazione locale nel computer dell'utente senza installare Office.

- Aggiungere o rimuovere lingue dall'installazione.

Si consiglia di utilizzare il file di Config.xml per configurare l'installazione di Skype for Business invisibile all'utente. 

Per impostazione predefinita, Config.xml file archiviato nella cartella di base del prodotto (ad esempio, \ _product_. WW) indica al programma di installazione di installare il prodotto. Ad esempio, il file Config.xml nella cartella seguente installa Skype for Business:

- \\server\share\Skype15\Skype.WW \Config.xml

Gli Config.xml più comunemente utilizzati per l'installazione di Skype for Business sono elencati nella tabella seguente.

**Config.xml elementi**


| **Elemento**              | **Descrizione**                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configurazione  <br/>     | Elemento di primo livello (obbligatorio). Contiene l'attributo Product, ad esempio: Product=Lync (funzionerà per i client Skype for Business)  <br/>                                                                                                                                                          |
| OptionState  <br/>       | Specifica come vengono gestite caratteristiche specifiche del prodotto durante l'installazione. Utilizzare gli attributi seguenti per impedire l'installazione di Servizi di integrazione applicativa, che include componenti condivisi che interferiscono con Outlook: <br/>  Id="LOBiMain" <br/>  State="Absent" <br/>  Children="Force" <br/> |
| Visualizza  <br/>           | Livello di interfaccia utente visualizzato all'utente dal programma di installazione. Di seguito sono riportati alcuni attributi tipici: <br/>  CompletionNotice="Yes"                                                                                                                                                                                |
| Registrazione  <br/>           | Opzioni per il tipo di registrazione eseguito dal programma di installazione. Di seguito sono riportati alcuni attributi tipici: <br/>  Type ="Off"                                                                                                                                                                                       |
| Impostazione  <br/>           | Specifica i valori per le proprietà di Windows Installer. Di seguito sono riportati alcuni attributi tipici: <br/>  Setting Id=" *name*" (nome della proprietà di Windows Installer)  <br/>  Valore=" *valore*" (valore da assegnare alla proprietà)  <br/>                                                             |
| DistributionPoint  <br/> | Percorso completo del punto di installazione di rete da cui deve essere eseguita l'installazione Include l'attributo Location: <br/>  Percorso=" *percorso*"  <br/>                                                                                                                                     |

L'esempio seguente mostra un file Config.xml per un'installazione invisibile all'utente tipica del client Skype for Business. 

```xml
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

Informazioni dettagliate sull'utilizzo del file Config.xml per eseguire le attività di installazione e manutenzione di Office sono disponibili all'indirizzo [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514) .

## <a name="to-customize-the-configxml-file"></a>Per personalizzare il Config.xml file

1. Aprire il Config.xml file utilizzando uno strumento di editor di testo, ad esempio Blocco note.

2. Individuare le righe che contengono gli elementi che si desidera modificare.

3. Modificare la voce dell'elemento con le opzioni invisibile all'utente che si desidera utilizzare. Assicurarsi di rimuovere i delimitatori di commento" \<!--" and "--\> ". Utilizzare ad esempio la sintassi seguente:

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. Salvare il file Config.xml.


