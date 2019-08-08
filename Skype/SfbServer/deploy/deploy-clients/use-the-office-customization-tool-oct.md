---
title: Usare lo strumento di personalizzazione di Office (ott) in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: 'Riepilogo: come usare lo strumento di personalizzazione di Office con il client Skype for business.'
ms.openlocfilehash: e7eb331c1b63a9e6a94ae3920e65ef57f426fbb0
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234842"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a>Usare lo strumento di personalizzazione di Office (ott) in Skype for Business Server
 
**Riepilogo:** Come usare lo strumento di personalizzazione di Office con il client Skype for business.
  
Lo strumento di personalizzazione di Office (ott) fa parte del programma di installazione ed è lo strumento consigliato per molte personalizzazioni. Usando lo strumento di personalizzazione di Office, è possibile personalizzare l'ufficio e salvare le personalizzazioni in un file msp di personalizzazione della configurazione. Si inserisce il file nella cartella Updates nel punto di installazione della rete. Durante l'installazione di Office, la configurazione Cerca un file di personalizzazione della configurazione nella cartella Updates e applica le personalizzazioni. La cartella Updates può essere usata solo per distribuire gli aggiornamenti software durante un'installazione iniziale di Office.
  
Lo strumento di personalizzazione di ottobre fa parte del programma di installazione e viene usato solo per le versioni con contratto multilicenza del prodotto. Si esegue lo strumento di personalizzazione `setup.exe /admin` di Office digitando la riga di comando dalla radice del punto di installazione di rete che contiene i file di origine. Ad esempio, usare quanto segue:
  
 ```
\\server\share\Office15\setup.exe /admin
```
  
Gli amministratori usano lo strumento di personalizzazione di ottobre per creare un file msp di personalizzazione della configurazione e possono personalizzare le aree seguenti:
  
- **Configurazione** Usato per specificare il percorso di installazione predefinito nel client e il nome dell'organizzazione predefinito, altre origini di installazione di rete, codice Product Key, contratto di licenza con l'utente finale, livello di visualizzazione, versioni precedenti di Office da rimuovere, programmi personalizzati da eseguire durante installazioni, impostazioni di sicurezza e proprietà di configurazione.
    
- **Caratteristiche** Consente di configurare le impostazioni utente e di personalizzare la modalità di installazione delle funzionalità di Office. Gli amministratori possono usare lo strumento di personalizzazione di Office per specificare i valori predefiniti iniziali delle impostazioni dell'applicazione per gli utenti. Gli utenti possono modificare la maggior parte delle impostazioni dopo l'installazione.
    
- **Contenuto aggiuntivo** Consente di aggiungere o rimuovere file, aggiungere o rimuovere voci del registro di sistema e configurare i tasti di scelta rapida.
    
- **Outlook** Usato per personalizzare il profilo di Outlook predefinito di un utente, specificare le impostazioni di Exchange, aggiungere account, rimuovere gli account ed esportare le impostazioni e specificare i gruppi di invio/ricezione.
    
Per informazioni su questo strumento, vedere [usare lo strumento di personalizzazione di Office per personalizzare la 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)). Tieni presente che queste informazioni si applicano anche alle versioni successive di Office.
  

