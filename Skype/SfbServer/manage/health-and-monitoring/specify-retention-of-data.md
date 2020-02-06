---
title: Specificare la conservazione dei dati CDR in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
description: 'Riepilogo: informazioni su come gestire i dati di registrazione dei dettagli delle chiamate (CDR) per Skype for Business Server.'
ms.openlocfilehash: 7cb9926ee8ec124b2fc75a69653c43c0150b6446
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817675"
---
# <a name="specify-retention-of-cdr-data-in-skype-for-business-server"></a>Specificare la conservazione dei dati CDR in Skype for Business Server
 
**Riepilogo:** Informazioni su come gestire i dati di registrazione dei dettagli delle chiamate (CDR) per Skype for Business Server.
  
Per impostazione predefinita, i dati della registrazione dei dettagli delle chiamate (CDR) vengono eliminati dopo 60 giorni. È possibile usare le impostazioni nella pagina **registrazione dettagli chiamata** per mantenere i dati per un periodo di tempo più lungo o più breve. Se si disattiva CDR, anche i dati acquisiti prima dell'abilitazione di CDR saranno soggetti all'eliminazione.
  
> [!NOTE]
> È necessario configurare CDR e la qualità dell'esperienza (QoE) per mantenere i dati per lo stesso numero di giorni. Ogni chiamata nei report dettagli chiamata (CDRs), disponibile dalla pagina Web monitoraggio report server, include informazioni CDR e QoE. Se la durata di eliminazione per CDR e QoE è diversa, alcune chiamate potrebbero includere solo dati CDR, mentre altre possono includere solo dati QoE. 
  
Usare le procedure seguenti per configurare le impostazioni di eliminazione dei dati CDR. 
  
### <a name="to-specify-retention-of-cdr-data"></a>Per specificare la conservazione dei dati CDR

1. Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. .
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.  
    
3. Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **registrazione dettagli chiamata**.
    
4. Nella pagina **registrazione dettagli chiamata** fare clic sul sito appropriato nella tabella, fare clic su **modifica**e quindi su **Mostra dettagli**.
    
5. Per attivare l'eliminazione, selezionare **Abilita l'eliminazione di CDRS**.
    
6. In **Mantieni CDRS per la durata massima (giorni):** selezionare il numero massimo di giorni in cui le registrazioni dei dettagli delle chiamate devono essere mantenute.
    
7. In **Mantieni i dati del report sugli errori per la durata massima (giorni):** selezionare il numero massimo di giorni in cui devono essere mantenuti i report degli errori.
    
8. Fare clic su **Commit**.
    
## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a>Specifica della conservazione CDR con i cmdlet di Windows PowerShell

È possibile creare impostazioni di conservazione CDR tramite Windows PowerShell e il cmdlet Set-CsCdrConfiguration. Puoi eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo di Blog ["Guida introduttiva: gestione di Microsoft Lync Server 2010 con Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Il processo è lo stesso in Skype for Business Server.
  
### <a name="to-specify-cdr-retention-for-a-specific-location"></a>Per specificare la conservazione CDR per una posizione specifica

- Questo comando consente l'eliminazione dei dati CDR per il sito Redmond e configura il sito per la gestione dei dati CDR e dei rapporti di errore per 20 giorni.
    
  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

### <a name="to-specify-cdr-retention-for-multiple-locations"></a>Per specificare la conservazione CDR per più posizioni

- Questo comando configura la conservazione CDR per tutte le impostazioni di configurazione CDR in uso in un'organizzazione.
    
  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .
  
## <a name="see-also"></a>Vedere anche

[Registrazione dei dettagli delle chiamate (CDR) in Skype for Business Server](call-detail-recording-cdr.md)
