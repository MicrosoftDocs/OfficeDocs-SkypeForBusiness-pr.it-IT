---
title: Usare le opzioni della riga di comando di configurazione con i client Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 'Riepilogo: informazioni sulle operazioni della riga di comando Setup. exe in configurazione di Office.'
ms.openlocfilehash: 2eee24f9ae79ed2f73e23c68883f2552902fb672
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195768"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a>Usare le opzioni della riga di comando di configurazione con i client Skype for business
 
**Riepilogo:** Informazioni sulle operazioni della riga di comando Setup. exe in configurazione di Office.
  
La riga di comando Setup. exe viene usata per pochissime operazioni in configurazione di Office. Invece di usare le opzioni della riga di comando per la configurazione, in genere si usa lo strumento di personalizzazione di Office e il file config. XML per la configurazione del prodotto e la personalizzazione delle funzionalità.
  
La riga di comando di Office Setup. exe riconosce le opzioni della riga di comando descritte nella tabella seguente.
  
**Opzioni della riga di comando per l'installazione di Office**

|**Opzione della riga di comando Setup**|**Descrizione**|
|:-----|:-----|
|/admin  <br/> |Esegue lo strumento di personalizzazione di Office per creare un file di personalizzazione della configurazione (file msp).  <br/> |
|/adminfile [percorso]  <br/> |Applica il file di personalizzazione della configurazione specificato all'installazione. È possibile specificare un percorso di un file di personalizzazione specifico (file msp) o nella cartella in cui vengono archiviati i file di personalizzazione.  <br/> |
|/config [percorso]  <br/> |Specifica il file config. XML usato dalla configurazione durante l'installazione. Usare l'opzione/config per specificare il file config. XML personalizzato per le installazioni di Skype for business, ad esempio:`/config \\server\share\Skype15\Skype.WW\Config.xml` <br/> |
|/Modify Skype  <br/> |Usato con un file config. xml modificato per eseguire la configurazione in modalità manutenzione e apportare modifiche a un'installazione di Office esistente. Ad esempio, puoi usare l'opzione/MODIFY per aggiungere o rimuovere le funzionalità di Skype for business.  <br/> |
|/Repair Skype  <br/> |Esegue la configurazione dal computer dell'utente per ripristinare Skype for business.  <br/> |
|/Uninstall Skype  <br/> |Esegue il programma di installazione per rimuovere Skype for business dal computer dell'utente.  <br/> |
   


