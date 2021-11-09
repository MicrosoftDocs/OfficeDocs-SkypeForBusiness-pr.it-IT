---
title: Utilizzare lo Strumento Office personalizzazione di Office in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: 'Riepilogo: come usare lo strumento Office personalizzazione con Skype for Business client.'
ms.openlocfilehash: c561fe9865d06b26ea46981bdf528515a465deea
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60830680"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a>Utilizzare lo Strumento Office personalizzazione di Office in Skype for Business Server
 
**Riepilogo:** Come usare lo strumento Office di personalizzazione con Skype for Business client.
  
Lo Strumento di personalizzazione di Office fa parte del programma di installazione ed è lo strumento consigliato per molte personalizzazioni. Tramite questo strumento, è possibile personalizzare Office e salvare le personalizzazioni in un file di configurazione dell'installazione con estensione msp. Il file viene inserito nella cartella Aggiornamenti nella posizione di installazione dalla rete. Quando si installa Office, il programma di installazione cerca un file di configurazione dell'installazione nella cartella Aggiornamenti e applica le personalizzazioni. La cartella Updates può essere utilizzata solo per distribuire gli aggiornamenti software durante un'installazione iniziale di Office.
  
Lo Strumento di personalizzazione di Office fa parte dell'installazione e viene utilizzato solo per le versioni con contratto multilicenza del prodotto. Lo Strumento di personalizzazione di Office viene eseguito digitando nella riga di comando dalla radice del punto di installazione di rete contenente i Office `setup.exe /admin` di origine. Ad esempio, utilizzare quanto segue:
  
 ```console
\\server\share\Office15\setup.exe /admin
```
  
Gli amministratori utilizzano lo Strumento di personalizzazione di Office per creare un file msp di personalizzazione dell'installazione e possono personalizzare le aree seguenti:
  
- **Installazione** Utilizzato per specificare il percorso di installazione predefinito nel client e nel nome dell'organizzazione predefinito, origini di installazione di rete aggiuntive, codice Product Key, contratto di licenza con l'utente finale, livello di visualizzazione, versioni precedenti di Office da rimuovere, programmi personalizzati da eseguire durante l'installazione, impostazioni di sicurezza e proprietà del programma di installazione.
    
- **Funzionalità** Usato per configurare le impostazioni utente e personalizzare la modalità Office di installazione delle funzionalità. Gli amministratori possono utilizzare lo Strumento di personalizzazione di Office per specificare valori predefiniti iniziali delle impostazioni delle applicazioni Office per gli utenti. Gli utenti possono modificare la maggior parte delle impostazioni dopo l'installazione.
    
- **Contenuto aggiuntivo** Usato per aggiungere o rimuovere file, aggiungere o rimuovere voci del Registro di sistema e configurare collegamenti.
    
- **Outlook** Utilizzato per personalizzare il profilo di Outlook predefinito di un utente, specificare le impostazioni Exchange, aggiungere account, rimuovere account ed esportare le impostazioni e specificare i gruppi di invio e ricezione.
    
Per informazioni sullo Strumento di personalizzazione di Office, vedere [Use the Oct to customize Office 2013.](/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)) Si noti che queste informazioni si applicano anche alle versioni successive di Office.
