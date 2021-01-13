---
title: Utilizzare Config.xml per eseguire le attività di installazione nei client Skype for business
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
description: 'Riepilogo: informazioni su come utilizzare il file Config.xml per specificare ulteriori istruzioni di installazione.'
ms.openlocfilehash: 1b8aeeb16e061e7816e475f01c9cd9a9146306ee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825186"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a>Utilizzare Config.xml per eseguire le attività di installazione nei client Skype for business

**Riepilogo:** Informazioni su come utilizzare il file di Config.xml per specificare ulteriori istruzioni di installazione.

Anche se lo strumento di personalizzazione di Office è lo strumento principale per l'installazione della personalizzazione, gli amministratori possono utilizzare il file Config.xml per specificare ulteriori istruzioni di installazione che non sono disponibili nel set di strumenti. È possibile eseguire le personalizzazioni seguenti solo mediante il file Config.xml:

- Specificare il percorso del punto di installazione di rete.

- Selezionare i prodotti da installare.

- Configurare la registrazione e il percorso del file di personalizzazione dell'installazione e degli aggiornamenti software.

- Specificare le opzioni di installazione, ad esempio il nome utente.

- Copiare l'origine di installazione locale nel computer dell'utente senza installare Office.

- Aggiungere o rimuovere lingue dall'installazione.

È consigliabile utilizzare il file Config.xml per configurare l'installazione invisibile di Skype for business. 

Per impostazione predefinita, il file di Config.xml memorizzato nella cartella di base del prodotto (ad esempio, \ _Product_. WW) indirizza il programma di installazione per l'installazione del prodotto. Ad esempio, il file Config.xml nella cartella seguente installa Skype for business:

- \\\Config.xml di server\share\Skype15\Skype.WW

Gli elementi di Config.xml più comunemente utilizzati per l'installazione di Skype for business sono elencati nella tabella seguente.

**ElementiConfig.xml**


| **Elemento**              | **Descrizione**                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configurazione  <br/>     | Elemento di primo livello (obbligatorio). Contiene l'attributo Product, ad esempio: Product = Lync (funzionerà per i client Skype for business)  <br/>                                                                                                                                                          |
| OptionState  <br/>       | Specifica come vengono gestite caratteristiche specifiche del prodotto durante l'installazione. Utilizzare gli attributi seguenti per impedire l'installazione di servizi di integrazione applicativa, che include componenti condivisi che interferiscono con Outlook: <br/>  ID = "LOBiMain" <br/>  Stato = "assente" <br/>  Children = "Force" <br/> |
| Visualizza  <br/>           | Livello di interfaccia utente visualizzato all'utente dal programma di installazione. Tra gli attributi tipici sono inclusi i seguenti: <br/>  CompletionNotice = "Sì"                                                                                                                                                                                |
| Registrazione  <br/>           | Opzioni per il tipo di registrazione eseguita dal programma di installazione. Tra gli attributi tipici sono inclusi i seguenti: <br/>  Type = "off"                                                                                                                                                                                       |
| Impostazione  <br/>           | Specifica i valori per le proprietà di Windows Installer. Tra gli attributi tipici sono inclusi i seguenti: <br/>  Setting ID = " *Name*" (il nome della proprietà di Windows Installer)  <br/>  Valore = " *valore*" (valore da assegnare alla proprietà)  <br/>                                                             |
| DistributionPoint  <br/> | Percorso completo del punto di installazione di rete da cui deve essere eseguita l'installazione Include l'attributo location: <br/>  Location = " *percorso*"  <br/>                                                                                                                                     |

Nell'esempio seguente viene mostrato un file di Config.xml per una tipica installazione invisibile all'utente del client Skype for business. 

```xml
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

Informazioni dettagliate sull'utilizzo del file di Config.xml per eseguire le attività di installazione e manutenzione di Office sono disponibili all'indirizzo [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514) .

## <a name="to-customize-the-configxml-file"></a>Per personalizzare il file di Config.xml

1. Aprire il file Config.xml utilizzando uno strumento di editor di testo, ad esempio il blocco note.

2. Individuare le righe che contengono gli elementi che si desidera modificare.

3. Modificare la voce dell'elemento con le opzioni Silent che si desidera utilizzare. Assicurarsi di rimuovere i delimitatori dei commenti " \<!--" and "--\> ". Utilizzare ad esempio la sintassi seguente:

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. Salvare il file Config.xml.


