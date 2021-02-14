---
title: Specificare la conservazione dei dati cdR in Skype for Business Server
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
ms.assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
description: 'Riepilogo: informazioni su come gestire i dati di registrazione dettagli chiamata (CDR) per Skype for Business Server.'
ms.openlocfilehash: 01b4765a9fa98a898255c1374115e17c4966e797
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814216"
---
# <a name="specify-retention-of-cdr-data-in-skype-for-business-server"></a>Specificare la conservazione dei dati cdR in Skype for Business Server
 
**Riepilogo:** Informazioni su come gestire i dati di registrazione dettagli chiamata (CDR) per Skype for Business Server.
  
Per impostazione predefinita, i dati di registrazione dettagli chiamata vengono eliminati dopo 60 giorni. È possibile utilizzare le impostazioni nella pagina **Registrazione dettagli chiamata** per mantenere i dati per un periodo maggiore o inferiore. Se si disabilita registrazione dettagli chiamata, verranno eliminati anche i dati acquisiti prima dell'abilitazione di registrazione dettagli chiamata.
  
> [!NOTE]
> È consigliabile configurare registrazione dettagli chiamata e QoE (Quality of Experience) in modo che mantengano i dati per lo stesso numero di giorni. Ogni chiamata inclusa nei rapporti Dettagli chiamata, disponibili dalla pagina Web dei rapporti di Monitoring Server, include informazioni di registrazione dettagli chiamata e QoE. Se la durata prima dell'eliminazione è diversa, alcune chiamate potrebbero includere solo dati di registrazione dettagli chiamata e altre solo dati QoE. 
  
Nelle procedure seguenti viene descritto come configurare le impostazioni per l'eliminazione dei dati di registrazione dettagli chiamata. 
  
### <a name="to-specify-retention-of-cdr-data"></a>Per specificare il periodo di mantenimento dei dati di registrazione dettagli chiamata

1. Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer nella rete in cui è stato distribuito Skype for Business Server.
    
2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.  
    
3. Sulla barra di spostamento sinistra fare clic su **Monitoraggio e archiviazione** e quindi su **Registrazione dettagli chiamata**.
    
4. Nella pagina **Registrazione dettagli chiamata** fare clic sul sito appropriato nella tabella, fare clic su **Modifica** e quindi su **Mostra dettagli**.
    
5. Per attivare l'eliminazione, selezionare **Abilita eliminazione registrazioni dettagli chiamata**.
    
6. In **Mantieni registrazioni dettagli chiamata per durata massima (giorni)** selezionare il numero massimo di giorni per cui mantenere le registrazioni dettagli chiamata.
    
7. In **Mantieni dati delle segnalazioni errori per durata massima (giorni)** selezionare il numero massimo di giorni per cui mantenere le segnalazioni degli errori.
    
8. Fare clic su **Commit**.
    
## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a>Impostazione della conservazione cdR tramite Windows PowerShell cmdlet

È possibile creare le impostazioni di mantenimento delle registrazioni dettagli chiamata utilizzando Windows PowerShell e il cmdlet Set-CsCdrConfiguration. È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'Windows PowerShell remoto per connettersi a Skype for Business Server, vedere l'articolo del blog ["Guida introduttiva: Gestione di Microsoft Lync Server 2010 tramite Remote PowerShell".](https://go.microsoft.com/fwlink/p/?linkId=255876) Il processo è lo stesso in Skype for Business Server.
  
### <a name="to-specify-cdr-retention-for-a-specific-location"></a>Per specificare il mantenimento delle registrazioni dettagli chiamata per una posizione specifica

- Questo comando consente di abilitare l'eliminazione dei dati delle registrazioni dettagli chiamata per il sito Redmond e di configurare il sito per mantenere sia tali dati che le segnalazioni di errore per 20 giorni.
    
  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

### <a name="to-specify-cdr-retention-for-multiple-locations"></a>Per specificare il mantenimento delle registrazioni dettagli chiamata per più posizioni

- Questo comando consente di configurare il mantenimento delle registrazioni dettagli chiamata per tutte le impostazioni di configurazione di tali registrazioni in uso in un'organizzazione.
    
  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsCdrConfiguration.](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)
  
## <a name="see-also"></a>Vedere anche

[Registrazione dettagli chiamata (CDR) in Skype for Business Server](call-detail-recording-cdr.md)
