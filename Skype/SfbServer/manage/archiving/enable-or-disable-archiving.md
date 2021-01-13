---
title: Abilitazione o disabilitazione dell'archiviazione in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: "Riepilogo: informazioni su come abilitare o disabilitare l'archiviazione in Skype for Business Server."
ms.openlocfilehash: 6d8f6f24bd4b10f7d33a00e218a494d6e8a823d1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817596"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a>Abilitazione o disabilitazione dell'archiviazione in Skype for Business Server

**Riepilogo:** Informazioni su come abilitare o disabilitare l'archiviazione in Skype for Business Server.
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a>Abilitazione o disabilitazione dell'archiviazione tramite il pannello di controllo

1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna. 
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server. 
    
3. Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Configurazione archiviazione**.
    
4. Selezionare la configurazione globale, del sito o del pool appropriata nell'elenco delle configurazioni di archiviazione, fare clic su **Modifica**, su **Mostra dettagli** e quindi eseguire le operazioni seguenti:
    
   - Per abilitare l'archiviazione solo per le sessioni di messaggistica istantanea, fare clic su **Archivia sessioni di messaggistica istantanea**.
    
   - Per abilitare l'archiviazione per le sessioni di messaggistica istantanea e le conferenze, fare clic su **Archivia sessioni di messaggistica istantanea e Web Conferencing**.
    
   - Per disabilitare l'archiviazione per la configurazione, fare clic su **Disattiva archiviazione**.
    
5. Fare clic su **Commit**.
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a>Abilitazione o disabilitazione dell'archiviazione tramite Windows PowerShell

È inoltre possibile abilitare o disabilitare l'archiviazione utilizzando il cmdlet **Set-CsArchivingConfiguration** . Ad esempio, il comando seguente consente di modificare tutte le impostazioni di configurazione di archiviazione in modo che vengano archiviate solo le sessioni di messaggistica istantanea. Il comando chiama il cmdlet **Get-CsArchivingConfiguration** senza parametri per restituire tutte le impostazioni di configurazione di archiviazione attualmente in uso nell'organizzazione. La raccolta viene quindi inviata tramite pipe al cmdlet **Where-Object** , che seleziona solo le impostazioni in cui la proprietà EnableArchiving è uguale a (-EQ) "ImAndWebConf". La raccolta filtrata viene quindi inviata tramite pipe al cmdlet **Set-CsArchivingConfiguration** , che accetta ogni elemento dell'insieme e modifica il valore di EnableArchiving in "ImOnly":
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```
