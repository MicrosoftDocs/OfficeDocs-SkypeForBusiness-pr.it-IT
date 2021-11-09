---
title: Utilizzare le opzioni della riga di comando del programma di installazione con Skype for Business client
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
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 'Riepilogo: informazioni sulle operazioni Setup.exe riga di comando in Office installazione.'
ms.openlocfilehash: 6a64ac821019f49f8cbb4988ad0e42da0363245b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60850480"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a>Utilizzare le opzioni della riga di comando del programma di installazione con Skype for Business client
 
**Riepilogo:** Informazioni sulle Setup.exe della riga di comando in Office installazione.
  
La riga di comando di Setup.exe consente di eseguire un numero limitato di operazioni di configurazione di Office. Anziché utilizzare le opzioni della riga di comando del programma di installazione, in genere si utilizzerà lo Strumento di personalizzazione di Office e il file Config.xml per l'installazione del prodotto e la personalizzazione delle funzionalità.
  
La riga di comando di Setup.exe di Office riconosce le opzioni descritte nella tabella seguente.
  
**Opzioni della riga di comando del programma di installazione di Office**

|**Opzione della riga di comando**|**Descrizione**|
|:-----|:-----|
|/admin  <br/> |Esegue lo Strumento di personalizzazione di Office per creare un file di personalizzazione della configurazione (file con estensione msp).  <br/> |
|/adminfile [percorso]  <br/> |Applica all'installazione il file di personalizzazione dell'installazione specificato. È possibile specificare il percorso di un determinato file di personalizzazione dell'installazione (msp) o della cartella in cui sono archiviati i file di personalizzazione.  <br/> |
|/config [percorso]  <br/> |Specifica il file Config.xml utilizzato durante l'installazione. Utilizzare l'opzione /config per specificare il file Config.xml personalizzato per Skype for Business installazioni, ad esempio:`/config \\server\share\Skype15\Skype.WW\Config.xml` <br/> |
|/modify Skype  <br/> |Utilizzato con un file Config.xml modificato per eseguire l'installazione in modalità manutenzione e apportare modifiche a un'installazione esistente di Office. Ad esempio, è possibile utilizzare l'opzione /modify per aggiungere o rimuovere Skype for Business funzionalità.  <br/> |
|/repair Skype  <br/> |Esegue il programma di installazione dal computer dell'utente per ripristinare Skype for Business.  <br/> |
|/uninstall Skype  <br/> |Esegue il programma di Skype for Business per rimuovere i dati dal computer dell'utente.  <br/> |
   


