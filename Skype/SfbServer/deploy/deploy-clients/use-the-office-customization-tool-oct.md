---
title: Usare lo Strumento di personalizzazione di Office in Skype for Business Server
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
description: 'Riepilogo: come usare lo Strumento di personalizzazione di Office con il client Skype for Business.'
ms.openlocfilehash: 32cd7951690ce5b1e38c20d83c8f53a9c48cd19c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100452"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a>Usare lo Strumento di personalizzazione di Office in Skype for Business Server
 
**Riepilogo:** Come usare lo Strumento di personalizzazione di Office con il client Skype for Business.
  
Lo Strumento di personalizzazione di Office fa parte del programma di installazione ed è lo strumento consigliato per molte personalizzazioni. Tramite questo strumento, è possibile personalizzare Office e salvare le personalizzazioni in un file di configurazione dell'installazione con estensione msp. Il file viene inserito nella cartella Aggiornamenti nella posizione di installazione dalla rete. Quando si installa Office, il programma di installazione cerca un file di configurazione dell'installazione nella cartella Aggiornamenti e applica le personalizzazioni. La cartella Updates può essere utilizzata solo per distribuire gli aggiornamenti software durante un'installazione iniziale di Office.
  
Lo Strumento di personalizzazione di Office fa parte dell'installazione e viene utilizzato solo per le versioni con contratto multilicenza del prodotto. Eseguire lo Strumento di personalizzazione di Office digitando nella riga di comando dalla radice del punto di installazione di rete  `setup.exe /admin` contenente i file di origine di Office. Ad esempio, utilizzare quanto segue:
  
 ```console
\\server\share\Office15\setup.exe /admin
```
  
Gli amministratori utilizzano lo Strumento di personalizzazione di Office per creare un file msp di personalizzazione dell'installazione e possono personalizzare le aree seguenti:
  
- **Installazione** Utilizzato per specificare il percorso di installazione predefinito nel client e nel nome dell'organizzazione predefinito, origini di installazione di rete aggiuntive, codice Product Key, contratto di licenza con l'utente finale, livello di visualizzazione, versioni precedenti di Office da rimuovere, programmi personalizzati da eseguire durante l'installazione, impostazioni di sicurezza e proprietà del programma di installazione.
    
- **Funzionalità** Utilizzato per configurare le impostazioni utente e personalizzare la modalità di installazione delle caratteristiche di Office. Gli amministratori possono utilizzare lo Strumento di personalizzazione di Office per specificare valori predefiniti iniziali delle impostazioni delle applicazioni Office per gli utenti. Gli utenti possono modificare la maggior parte delle impostazioni dopo l'installazione.
    
- **Contenuto aggiuntivo** Usato per aggiungere o rimuovere file, aggiungere o rimuovere voci del Registro di sistema e configurare collegamenti.
    
- **Outlook** Utilizzato per personalizzare il profilo outlook predefinito di un utente, specificare le impostazioni di Exchange, aggiungere account, rimuovere account ed esportare le impostazioni e specificare Send\Receive groups.
    
Per informazioni sullo Strumento di personalizzazione di Office, vedere [Utilizzare lo Strumento di personalizzazione di Office per personalizzare Office 2013.](/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)) Si noti che queste informazioni si applicano anche alle versioni successive di Office.
