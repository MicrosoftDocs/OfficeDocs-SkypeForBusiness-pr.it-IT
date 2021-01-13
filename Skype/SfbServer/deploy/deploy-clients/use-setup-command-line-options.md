---
title: Utilizzare le opzioni della riga di comando del programma di installazione con i client Skype for business
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
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 'Riepilogo: informazioni su Setup.exe operazioni della riga di comando nel programma di installazione di Office.'
ms.openlocfilehash: 042ba2bdea6228f7c8a726c0bdb2ca5c3233d5f4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837206"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a>Utilizzare le opzioni della riga di comando del programma di installazione con i client Skype for business
 
**Riepilogo:** Informazioni su Setup.exe operazioni della riga di comando nel programma di installazione di Office.
  
La riga di comando di Setup.exe consente di eseguire un numero limitato di operazioni di configurazione di Office. Invece di utilizzare le opzioni della riga di comando del programma di installazione, in genere viene utilizzato lo strumento di personalizzazione di Office e il file di Config.xml per l'installazione del prodotto e la personalizzazione delle funzionalità.
  
La riga di comando di Setup.exe di Office riconosce le opzioni descritte nella tabella seguente.
  
**Opzioni della riga di comando del programma di installazione di Office**

|**Opzione della riga di comando**|**Descrizione**|
|:-----|:-----|
|/admin  <br/> |Esegue lo Strumento di personalizzazione di Office per creare un file di personalizzazione della configurazione (file con estensione msp).  <br/> |
|/adminfile [percorso]  <br/> |Applica all'installazione il file di personalizzazione dell'installazione specificato. È possibile specificare il percorso di un determinato file di personalizzazione dell'installazione (msp) o della cartella in cui sono archiviati i file di personalizzazione.  <br/> |
|/config [percorso]  <br/> |Specifica il file Config.xml utilizzato durante l'installazione. Utilizzare l'opzione/config per specificare il file Config.xml personalizzato per le installazioni di Skype for business, ad esempio:  `/config \\server\share\Skype15\Skype.WW\Config.xml` <br/> |
|/Modify Skype  <br/> |Utilizzato con un file Config.xml modificato per eseguire l'installazione in modalità manutenzione e apportare modifiche a un'installazione esistente di Office. Ad esempio, è possibile utilizzare l'opzione/MODIFY per aggiungere o rimuovere le caratteristiche di Skype for business.  <br/> |
|/Repair Skype  <br/> |Esegue il programma di installazione dal computer dell'utente per ripristinare Skype for business.  <br/> |
|/Uninstall Skype  <br/> |Esegue il programma di installazione per rimuovere Skype for business dal computer dell'utente.  <br/> |
   


