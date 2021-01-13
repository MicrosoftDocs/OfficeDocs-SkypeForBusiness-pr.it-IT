---
title: Utilizzare lo strumento di personalizzazione di Office in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: 'Riepilogo: informazioni su come utilizzare lo strumento di personalizzazione di Office con il client Skype for business.'
ms.openlocfilehash: ba99f0556f3fb1d0e0f6870d1eaa7a3d2108b4d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812566"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a>Utilizzare lo strumento di personalizzazione di Office in Skype for Business Server
 
**Riepilogo:** Come usare lo strumento di personalizzazione di Office con il client Skype for business.
  
Lo Strumento di personalizzazione di Office fa parte del programma di installazione ed è lo strumento consigliato per molte personalizzazioni. Tramite questo strumento, è possibile personalizzare Office e salvare le personalizzazioni in un file di configurazione dell'installazione con estensione msp. Il file viene inserito nella cartella Aggiornamenti nella posizione di installazione dalla rete. Quando si installa Office, il programma di installazione cerca un file di configurazione dell'installazione nella cartella Aggiornamenti e applica le personalizzazioni. La cartella Updates può essere utilizzata solo per distribuire gli aggiornamenti software durante un'installazione iniziale di Office.
  
Lo strumento di personalizzazione di Office è parte del programma di installazione e viene utilizzato solo per le versioni con contratto multilicenza del prodotto. Per eseguire lo strumento di personalizzazione di Office, digitare la  `setup.exe /admin` riga di comando dalla radice del punto di installazione di rete che contiene i file di origine dell'ufficio. Ad esempio, utilizzare quanto segue:
  
 ```console
\\server\share\Office15\setup.exe /admin
```
  
Gli amministratori utilizzano lo strumento di personalizzazione di Office per creare un file msp di personalizzazione dell'installazione e possono personalizzare le aree seguenti:
  
- **Programma di installazione** Utilizzato per specificare il percorso di installazione predefinito sul client e il nome dell'organizzazione predefinito, origini di installazione di rete aggiuntive, codice Product Key, contratto di licenza con l'utente finale, livello di visualizzazione, versioni precedenti di Office da rimuovere, programmi personalizzati da eseguire durante l'installazione, impostazioni di sicurezza e proprietà del programma di installazione.
    
- **Caratteristiche** Utilizzato per configurare le impostazioni utente e per personalizzare la modalità di installazione delle caratteristiche di Office. Gli amministratori possono utilizzare lo Strumento di personalizzazione di Office per specificare valori predefiniti iniziali delle impostazioni delle applicazioni Office per gli utenti. Gli utenti possono modificare la maggior parte delle impostazioni dopo l'installazione.
    
- **Contenuto aggiuntivo** Utilizzato per aggiungere o rimuovere file, aggiungere o rimuovere voci del registro di sistema e configurare i collegamenti.
    
- **Outlook** Utilizzato per personalizzare il profilo Outlook predefinito di un utente, specificare le impostazioni di Exchange, aggiungere account, rimuovere account ed esportare le impostazioni e specificare i gruppi di invio/ricezione.
    
Per informazioni sullo strumento [di personalizzazione di Office, vedere Use the Oct to Customize ufficio 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)). Si noti che queste informazioni si applicano anche alle versioni successive di Office.
  

