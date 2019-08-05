---
title: Gestire i servizi per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c99ee134-8294-4481-bb4e-710fe85a39ca
description: Questo articolo descrive come gestire i servizi in uso in una topologia di Skype for Business Server.
ms.openlocfilehash: 9d1a79226422da57eee36e27590769f76b89b560
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188618"
---
# <a name="manage-services-for-skype-for-business-server"></a>Gestire i servizi per Skype for Business Server

Questo articolo descrive come gestire i servizi in uso in una topologia di Skype for Business Server.
  
## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>Visualizzare un elenco di computer che eseguono Skype for Business Server
<a name="view_list"> </a>

Puoi usare il pannello di controllo di Skype for Business Server per visualizzare un elenco di tutti i computer che eseguono Skype for Business Server nella tua topologia e vedere lo stato del servizio di ognuno di essi. È possibile ordinare l'elenco in base al computer, al pool o al sito. 
  
### <a name="to-view-a-list-of-computers-running-skype-for-business-server"></a>Per visualizzare un elenco di computer che eseguono Skype for Business Server

1. Da un account utente assegnato a uno dei ruoli amministrativi predefiniti per Skype for Business Server, accedere a qualsiasi computer della distribuzione interna. Per informazioni dettagliate sui ruoli amministrativi predefiniti disponibili in Skype for Business Server, vedere **pianificazione per il controllo dell'accesso basato sui ruoli**.   
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.   
3. Nella barra di spostamento sinistra fare clic **** su topologia e quindi su **stato**.   
4. Nella pagina **stato** eseguire una delle operazioni seguenti in base alle esigenze:
   - Ordinare l'elenco facendo clic sul titolo del **computer**, del **pool**o della colonna del **sito** , quindi facendo clic sulla freccia su o freccia giù. 
   - Fare clic su **Aggiorna** per visualizzare l'elenco più aggiornato.  
   - Cercare un computer specifico digitando il nome del computer nel campo di ricerca.
    
## <a name="view-the-status-of-services-running-on-a-skype-for-business-server"></a>Visualizzare lo stato dei servizi in uso in un server Skype for business
<a name="view-status"> </a>

Puoi usare il pannello di controllo di Skype for Business Server per visualizzare tutti i servizi in uso in un computer specifico nella topologia di Skype for Business Server e vedere lo stato di ogni servizio.
  
### <a name="to-view-the-status-of-services-running-on-a-computer"></a>Per visualizzare lo stato dei servizi in uso in un computer

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 
3. Nella barra di spostamento sinistra fare clic **** su topologia. 
4. Nella pagina **stato** ordinare o cercare l'elenco, se necessario, per trovare il computer interessato e quindi fare clic sul nome del computer.
5. Eseguire una delle operazioni seguenti:
   - Per visualizzare lo stato più recente dei servizi in uso nel computer, fare clic su **Ottieni stato servizio**.
   - Per visualizzare un elenco di servizi specifici in uso nel computer e lo stato di ogni servizio, fare clic su **Proprietà**e quindi su **Chiudi** per tornare all'elenco.
    
### <a name="viewing-service-status-with-windows-powershell-cmdlets"></a>Visualizzazione dello stato del servizio con i cmdlet di Windows PowerShell

È anche possibile visualizzare lo stato del servizio tramite Windows PowerShell e il cmdlet **Get-CsWindowsService** . Puoi eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo di Blog ["Guida introduttiva: gestione di Microsoft Lync Server 2010 con Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Il processo è lo stesso in Skype for Business Server.
  
### <a name="to-view-service-status"></a>Per visualizzare lo stato del servizio

Per visualizzare lo stato del servizio in un computer, digitare un comando simile al seguente in Skype for Business Server Management Shell e quindi premere INVIO:
  
```
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

Questo comando restituisce informazioni simili a quelle seguenti:
  
|**RoleName**|**Stato**|
|:-----|:-----|
|W3SVC  <br/> |Esecuzione  <br/> |
|{CentralManagement}  <br/> | Esecuzione <br/> |
|{ClsAgent}  <br/> |Esecuzione  <br/> |
|{Registrar, UserServer, EdgeServer}  <br/> |Esecuzione  <br/> |
|ApplicationServer  <br/> |Esecuzione  <br/> |
|ConferencingServer  <br/> |Esecuzione  <br/> |
|MediationServer  <br/> |Esecuzione  <br/> |
   
Per informazioni dettagliate, vedere [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/get-cswindowsservice.md?view=skype-ps).
  
## <a name="view-details-about-a-service"></a>Visualizzare i dettagli di un servizio
<a name="view_details"> </a>

Puoi usare il pannello di controllo di Skype for Business Server per visualizzare i dettagli su ogni servizio in uso in un computer specifico della topologia. È possibile visualizzare lo stato di ogni servizio e i dettagli, ad esempio i database associati, le porte e i servizi dipendenti.
  
### <a name="to-view-details-for-a-service"></a>Per visualizzare i dettagli di un servizio

1. Da un account utente assegnato a uno dei ruoli amministrativi predefiniti per Skype for Business Server, accedere a qualsiasi computer della distribuzione interna. Per informazioni dettagliate sui ruoli amministrativi predefiniti disponibili in Skype for Business Server, vedere **pianificazione per il controllo dell'accesso basato sui ruoli**.
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 
3. Nella barra di spostamento sinistra fare clic **** su topologia e quindi su **stato**.
4. Nella pagina **stato** ordinare o eseguire una ricerca nell'elenco e quindi fare clic sul computer che si vuole visualizzare.
5. Fare clic su **Proprietà**.
6. Nella finestra **Visualizza dettaglio computer** ordinare l'elenco dei servizi, se necessario, e fare clic sul servizio che si vuole visualizzare.
7. Eseguire una delle operazioni seguenti in base alle esigenze:
   - Per visualizzare lo stato più recente di tale servizio specifico, fare clic su **Ottieni stato servizio**.
   - Per visualizzare i dettagli del servizio specifico, fare clic su **Proprietà** e quindi su **Chiudi**.
   - Per tornare all'elenco di tutti i computer della topologia, fare clic su **Chiudi**.
    
## <a name="start-or-stop-skype-for-business-server-services"></a>Avviare o arrestare i servizi di Skype for Business Server
<a name="StartStop"> </a>

Puoi usare il pannello di controllo di Skype for Business Server per avviare o arrestare tutti i servizi di Skype for Business Server in uso in un computer specifico oppure per avviare o arrestare un servizio specifico.
  
### <a name="to-start-or-stop-all-skype-for-business-services-on-a-computer"></a>Per avviare o arrestare tutti i servizi Skype for business in un computer

1. Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. . Per determinare se è stato assegnato il ruolo CsServerAdministrator o CsAdministrator RBAC, è possibile eseguire un comando simile al seguente:
    
   ```
   Get-CsAdminRoleAssignment -Identity "kenmyer"
   ```

2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 
3. Nella barra di spostamento sinistra fare clic **** su topologia e quindi su **stato**.
4. Nella pagina **stato** ordinare o cercare l'elenco in base alle esigenze per trovare il computer in cui sono in esecuzione i servizi che si desidera avviare o arrestare e quindi fare clic su di esso.
5. Fare clic su **azione**.
6. Fare clic su **Avvia tutti i servizi** o **arrestare tutti i servizi**.
    
### <a name="to-start-or-stop-a-specific-service"></a>Per avviare o arrestare un servizio specifico

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 
3. Nella barra di spostamento sinistra fare clic **** su topologia e quindi su **stato**.
4. Nella pagina **stato** ordinare o cercare l'elenco in base alle esigenze per trovare il computer in cui è in esecuzione il servizio che si vuole avviare o arrestare e quindi fare clic su di esso.
5. Fare clic su **Proprietà**.
6. Ordinare l'elenco dei servizi, se necessario, e fare clic sul servizio che si vuole avviare o arrestare.
7. Fare clic su **azione**.
8. Fare clic su **Avvia servizio** o **Interrompi servizio**.
9. Fare clic su **Chiudi**.
    
## <a name="prevent-sessions-for-services"></a>Impedire sessioni per i servizi
<a name="prevent_session"> </a>

Puoi usare il pannello di controllo di Skype for Business Server per evitare nuove sessioni per tutti i servizi di Skype for Business Server in uso in uno specifico computer o per evitare nuove sessioni per un servizio specifico di Skype for Business Server.
  
### <a name="to-prevent-new-sessions-for-all-skype-for-business-services-on-a-computer"></a>Per evitare nuove sessioni per tutti i servizi Skype for business in un computer

1. Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. .
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 
3. Nella barra di spostamento sinistra fare clic **** su topologia e quindi su **stato**.
4. Nella pagina **stato** ordinare o cercare l'elenco in base alle esigenze per trovare il computer in cui sono in esecuzione i servizi per cui si vogliono impedire le nuove sessioni e quindi fare clic su di esso.
5. Fare clic su **azione**.
6. Fare clic su **Impedisci nuove sessioni per tutti i servizi**.
    
### <a name="to-prevent-new-sessions-for-a-specific-service"></a>Per impedire nuove sessioni per un servizio specifico

1. Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. .
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 
3. Nella barra di spostamento sinistra fare clic **** su topologia e quindi su **stato**.
4. Nella pagina **stato** ordinare o cercare l'elenco in base alle esigenze per trovare il computer in cui è in esecuzione il servizio che si vuole avviare o arrestare e quindi fare clic su di esso. 
5. Fare clic su **Proprietà**.
6. Ordinare l'elenco dei servizi, se necessario, e fare clic sul servizio per cui si vogliono impedire le nuove sessioni.
7. Fare clic su **azione**.
8. Fare clic su **Impedisci nuove sessioni per il servizio**.
9. Fare clic su **Chiudi**.
    

