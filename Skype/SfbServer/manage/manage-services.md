---
title: Gestire i servizi per Skype for Business Server
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
ms.assetid: c99ee134-8294-4481-bb4e-710fe85a39ca
description: In questo articolo viene descritto come gestire i servizi in esecuzione in Skype for Business Server topologia.
ms.openlocfilehash: ac09cc3d387fb74c28a1908489071a739fa1bbc65d5d1f6e53758db61b0cbf29
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54295413"
---
# <a name="manage-services-for-skype-for-business-server"></a>Gestire i servizi per Skype for Business Server

In questo articolo viene descritto come gestire i servizi in esecuzione in Skype for Business Server topologia.
  
## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>Visualizzare un elenco di computer che eseguono Skype for Business Server
<a name="view_list"> </a>

È possibile utilizzare Skype for Business Server di controllo per visualizzare un elenco di tutti i computer che eseguono Skype for Business Server nella topologia e visualizzare lo stato del servizio di ognuno di essi. È possibile ordinare l'elenco in base al computer, al pool o al sito. 
  
### <a name="to-view-a-list-of-computers-running-skype-for-business-server"></a>Per visualizzare un elenco di computer che eseguono Skype for Business Server

1. Da un account utente assegnato a uno dei ruoli amministrativi predefiniti per Skype for Business Server, accedere a qualsiasi computer nella distribuzione interna. Per informazioni dettagliate sui ruoli amministrativi predefiniti disponibili in Skype for Business Server, vedere **Planning for Role-Based Access Control**.   
2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo.   
3. Nella barra di spostamento sinistra fare clic su **Topologia** e quindi su **Stato**.   
4. Nella pagina **Stato** eseguire le operazioni seguenti in base alle esigenze:
   - Ordinare l'elenco facendo clic sull'intestazione di colonna **Computer**, **Pool** o **Sito** e quindi sulla freccia verso l'alto o verso il basso. 
   - Fare clic su **Aggiorna** per visualizzare l'elenco più aggiornato.  
   - Cercare un computer specifico digitando il relativo nome nel campo di ricerca.
    
## <a name="view-the-status-of-services-running-on-a-skype-for-business-server"></a>Visualizzare lo stato dei servizi in esecuzione in un Skype for Business server
<a name="view-status"> </a>

È possibile utilizzare Skype for Business Server di controllo per visualizzare tutti i servizi in esecuzione in un computer specifico nella topologia di Skype for Business Server e visualizzare lo stato di ogni servizio.
  
### <a name="to-view-the-status-of-services-running-on-a-computer"></a>Per visualizzare lo stato dei servizi in esecuzione in un computer

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo. 
3. Sulla barra di spostamento sinistra fare clic su **Topologia**. 
4. Nella pagina **Stato** ordinare o cercare l'elenco in base alle esigenze per trovare il computer a cui si è interessati e quindi fare clic sul nome del computer.
5. Effettuare una delle operazioni seguenti:
   - Per visualizzare lo stato più recente dei servizi in esecuzione sul computer, fare clic su **Ottieni stato servizio**.
   - Per visualizzare un elenco di servizi specifici in esecuzione sul computer e lo stato di ogni servizio, fare clic su **Proprietà** e quindi su **Chiudi** per tornare all'elenco.
    
### <a name="viewing-service-status-with-windows-powershell-cmdlets"></a>Visualizzazione dello stato del servizio Windows cmdlet di PowerShell

È inoltre possibile visualizzare lo stato del servizio utilizzando Windows PowerShell e il cmdlet **Get-CsWindowsService.** È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'Windows PowerShell per connettersi a Skype for Business Server, vedere l'articolo del blog ["Guida introduttiva: Gestione di Microsoft Lync Server 2010 tramite Remote PowerShell".](https://go.microsoft.com/fwlink/p/?linkId=255876) Il processo è lo stesso in Skype for Business Server.
  
### <a name="to-view-service-status"></a>Per visualizzare lo stato del servizio

Per visualizzare lo stato del servizio in un computer, digitare un comando simile al seguente in Skype for Business Server Management Shell e quindi premere INVIO:
  
```PowerShell
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

Il comando restituisce informazioni simili a quelle riportate di seguito:
  
|**RoleName**|**Stato**|
|:-----|:-----|
|{W3SVC}  <br/> |In esecuzione  <br/> |
|{CentralManagement}  <br/> | In esecuzione <br/> |
|{ClsAgent}  <br/> |In esecuzione  <br/> |
|{Registrar, UserServer, EdgeServer}  <br/> |In esecuzione  <br/> |
|{ApplicationServer}  <br/> |In esecuzione  <br/> |
|{ConferencingServer}  <br/> |In esecuzione  <br/> |
|{MediationServer}  <br/> |In esecuzione  <br/> |
   
Per informazioni dettagliate, [vedere Get-CsWindowsService](/powershell/module/skype/get-cswindowsservice.md?view=skype-ps).
  
## <a name="view-details-about-a-service"></a>Visualizzare i dettagli su un servizio
<a name="view_details"> </a>

È possibile utilizzare Skype for Business Server pannello di controllo per visualizzare i dettagli su ogni servizio in esecuzione in un computer specifico della topologia. È possibile visualizzare lo stato di ogni servizio e i dettagli, ad esempio i database, le porte e i servizi dipendenti associati.
  
### <a name="to-view-details-for-a-service"></a>Per visualizzare i dettagli di un servizio

1. Da un account utente assegnato a uno dei ruoli amministrativi predefiniti per Skype for Business Server, accedere a qualsiasi computer nella distribuzione interna. Per informazioni dettagliate sui ruoli amministrativi predefiniti disponibili in Skype for Business Server, vedere **Planning for Role-Based Access Control**.
2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo. 
3. Nella barra di spostamento sinistra fare clic su **Topologia** e quindi su **Stato**.
4. Nella pagina **Stato** ordinare o cercare nell'elenco e quindi fare clic sul computer che si desidera visualizzare.
5. Fare clic su **Proprietà**.
6. Nella finestra **Visualizza dettagli computer** ordinare l'elenco dei servizi, se necessario, e fare clic sul servizio che si desidera visualizzare.
7. Eseguire una delle operazioni seguenti in base alle esigenze:
   - Per visualizzare lo stato più recente del servizio specifico, fare clic **su Ottieni stato servizio**.
   - Per visualizzare i dettagli relativi al servizio specifico, fare clic **su Proprietà** e quindi su **Chiudi.**
   - Per tornare all'elenco di tutti i computer della topologia, fare clic su **Chiudi.**
    
## <a name="start-or-stop-skype-for-business-server-services"></a>Avviare o arrestare Skype for Business Server servizi
<a name="StartStop"> </a>

È possibile utilizzare il Skype for Business Server di controllo per avviare o arrestare tutti i servizi Skype for Business Server in esecuzione in un computer specifico oppure per avviare o arrestare un servizio specifico.
  
### <a name="to-start-or-stop-all-skype-for-business-services-on-a-computer"></a>Per avviare o arrestare tutti i Skype for Business in un computer

1. Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer nella rete in cui è stato distribuito Skype for Business Server. È possibile determinare se è stato assegnato il ruolo CsServerAdministrator o CsAdministrator RBAC eseguendo un comando simile al seguente:
    
   ```PowerShell
   Get-CsAdminRoleAssignment -Identity "kenmyer"
   ```

2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo. 
3. Nella barra di spostamento sinistra fare clic su **Topologia** e quindi su **Stato**.
4. Nella pagina **Stato** ordinare o scorrere l'elenco per trovare il computer in cui sono in esecuzione i servizi che si desidera avviare o arrestare e quindi fare clic su di esso.
5. Fare clic su **Azione**.
6. Fare clic su **Avvia tutti i servizi** o **Arresta tutti i servizi**.
    
### <a name="to-start-or-stop-a-specific-service"></a>Per avviare o arrestare un servizio specifico

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo. 
3. Nella barra di spostamento sinistra fare clic su **Topologia** e quindi su **Stato**.
4. Nella pagina **Stato** ordinare o scorrere l'elenco per trovare il computer in cui è in esecuzione il servizio che si desidera avviare o arrestare e quindi fare clic su di esso.
5. Fare clic su **Proprietà**.
6. Ordinare l'elenco dei servizi, se necessario, e fare clic sul servizio da avviare o arrestare.
7. Fare clic su **Azione**.
8. Fare clic su **Avvia servizio** o **Arresta servizio**.
9. Fare clic su **Chiudi**.
    
## <a name="prevent-sessions-for-services"></a>Impedire le sessioni per i servizi
<a name="prevent_session"> </a>

È possibile utilizzare il Skype for Business Server di controllo per impedire nuove sessioni per tutti i servizi Skype for Business Server in esecuzione in un computer specifico o per impedire nuove sessioni per un servizio Skype for Business Server specifico.
  
### <a name="to-prevent-new-sessions-for-all-skype-for-business-services-on-a-computer"></a>Per impedire nuove sessioni per tutti i Skype for Business in un computer

1. Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer nella rete in cui è stato distribuito Skype for Business Server.
2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo. 
3. Sulla barra di spostamento sinistra fare clic su **Topologia** e quindi su **Stato**.
4. Nella pagina **Stato** ordinare l'elenco oppure cercare nell'elenco il computer in cui sono in esecuzione i servizi per cui si desidera impedire nuove sessioni, quindi fare clic su di esso.
5. Fare clic su **Azione**.
6. Fare clic su **Impedisci nuove sessioni per tutti i servizi**.
    
### <a name="to-prevent-new-sessions-for-a-specific-service"></a>Per impedire nuove sessioni per uno specifico servizio

1. Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer nella rete in cui è stato distribuito Skype for Business Server.
2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo. 
3. Nella barra di spostamento sinistra fare clic su **Topologia** e quindi su **Stato**.
4. Nella pagina **Stato** ordinare o scorrere l'elenco per trovare il computer in cui è in esecuzione il servizio che si desidera avviare o arrestare e quindi fare clic su di esso. 
5. Fare clic su **Proprietà**.
6. Ordinare l'elenco dei servizi, se necessario, quindi fare clic sul servizio per cui si desidera impedire nuove sessioni.
7. Fare clic su **Azione**.
8. Fare clic su **Impedisci nuove sessioni per il servizio**.
9. Fare clic su **Chiudi**.
