---
title: Abilitare o disabilitare l'archiviazione in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: "Riepilogo: informazioni su come abilitare o disabilitare l'archiviazione in Skype for Business Server."
ms.openlocfilehash: 0e4ef4dde27ffa5856f2b73b69ffbadc24399c59
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190373"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a>Abilitare o disabilitare l'archiviazione in Skype for Business Server

**Riepilogo:** Informazioni su come abilitare o disabilitare l'archiviazione in Skype for Business Server.
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a>Abilitare o disabilitare l'archiviazione tramite il pannello di controllo

1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna. 
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 
    
3. Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**e quindi su **Configurazione archiviazione**.
    
4. Selezionare la configurazione globale, del sito o del pool appropriata dall'elenco delle configurazioni di archiviazione, fare clic su **modifica**, fare clic su **Mostra dettagli**e quindi eseguire le operazioni seguenti:
    
   - Per abilitare l'archiviazione solo per le sessioni di messaggistica istantanea (IM), fare clic su **Archivia sessioni**istantanee.
    
   - Per abilitare l'archiviazione sia per le sessioni di messaggistica istantanea che per le conferenze, fare clic su **Archivia sessioni di messaggistica istantanea e conferenza**.
    
   - Per disabilitare l'archiviazione per la configurazione, fare clic su **Disattiva archiviazione**.
    
5. Fare clic su **Commit**.
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a>Abilitare o disabilitare l'archiviazione tramite Windows PowerShell

È anche possibile abilitare o disabilitare l'archiviazione usando il cmdlet **Set-CsArchivingConfiguration** . Ad esempio, il comando seguente modifica tutte le impostazioni di configurazione dell'archiviazione in modo che vengano archiviate solo le sessioni di messaggistica istantanea. Il comando chiama il cmdlet **Get-CsArchivingConfiguration** senza parametri per restituire tutte le impostazioni di configurazione dell'archiviazione attualmente in uso nell'organizzazione. La raccolta viene quindi inviata tramite pipe al cmdlet **Where-Object** , che seleziona solo le impostazioni in cui la proprietà EnableArchiving è uguale a (-EQ) "ImAndWebConf". La raccolta filtrata viene quindi inviata tramite pipe al cmdlet **Set-CsArchivingConfiguration** , che accetta ogni elemento della raccolta e modifica il valore di EnableArchiving in "ImOnly":
  
```
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```
