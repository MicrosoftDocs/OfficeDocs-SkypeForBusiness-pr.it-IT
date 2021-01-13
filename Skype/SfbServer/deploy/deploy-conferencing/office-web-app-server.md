---
title: Configurare l'integrazione con il server Office Web Apps in Skype for Business Server
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
ms.assetid: b7e9149e-bf16-4120-afe0-3ee09c88f5eb
description: "Riepilogo: leggere questo argomento per informazioni su come configurare l'integrazione tra il server Office Web Apps e Skype for Business Server per abilitare le presentazioni di PowerPoint per le conferenze Web."
ms.openlocfilehash: 005bd9fe7d7fece7d488935002e7146fc5a9ffe4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820466"
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server"></a>Configurare l'integrazione con il server Office Web Apps in Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per informazioni su come configurare l'integrazione tra il server Office Web Apps e Skype for Business Server per abilitare le presentazioni di PowerPoint per le conferenze Web.
  
Skype for Business Server utilizza il server Office Web Apps per gestire le presentazioni di PowerPoint per le conferenze Web. Per informazioni sui vantaggi di questo approccio, vedere [Plan for Conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md).
  
Prima di poter configurare Skype for Business Server per l'utilizzo del server Office Web Apps, è necessario assicurarsi che il server Office Web Apps sia già stato distribuito e configurato. Per informazioni sul server Office Web Apps, vedere l'articolo [deploy the Infrastructure: Office Online Server](https://go.microsoft.com/fwlink/p/?linkid=257525). 
  
Dopo l'installazione del server Office Web Apps e la Web farm correttamente configurata, è necessario configurare Skype for Business Server per comunicare con il nuovo server aggiungendo l'URL di individuazione del server Office Web Apps alla topologia di Skype for Business Server. 
  
> [!NOTE]
> L'ultima iterazione del server Office Web Apps è denominata Office Online Server, che è supportato da Skype for Business Server. Per ulteriori informazioni, fare riferimento alla [documentazione di Office Online Server](https://technet.microsoft.com/library/jj219456%28v=office.16%29.aspx). 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a>Configurare Skype for Business Server per la comunicazione con il server Office Web Apps

Per aggiungere il server Office Web Apps alla topologia, eseguire le operazioni seguenti:
  
1. Aprire Generatore di topologie di Skype for Business Server.
    
2. Nella finestra di dialogo **Generatore di topologie** selezionare **Scarica topologia dalla distribuzione esistente** e quindi fare clic su **OK**.
    
3. Nella casella **Salva topologia con nome** digitare un nome per il documento della topologia (ad esempio **TopologiaPreServerWebApps**) nella casella **Nome file** e quindi fare clic su **Salva**. Questa topologia potrà essere recuperata e ripubblicata in seguito se si verificano problemi con la nuova topologia.
    
4. In Generatore di topologie espandere **Skype for Business Server**, espandere il nome del sito, espandere **pool Enterprise Edition front end**, fare clic con il pulsante destro del mouse sul nome di uno dei pool e quindi scegliere **modifica proprietà**.
    
5. Nella scheda **Generale** della finestra di dialogo **Modifica proprietà** individuare il titolo **Associa il pool a un server Office Web Apps** e quindi fare clic su **Nuovo** oppure selezionare un server Office Web Apps esistente nell'elenco a discesa.
    
6. Nella finestra di dialogo **Definire un nuovo server Office Web Apps** digitare il nome di dominio completo (FQDN) del computer del server Office Web Apps nella casella **FQDN server Office Web Apps**. L'URL di individuazione del server Office Web Apps dovrebbe comparire così automaticamente nella casella **URL di individuazione server Office Web Apps**.
    
   - Se il server Office Web Apps è installato in locale e nella stessa area di rete di Skype for Business Server, l'opzione **Server Office Web Apps è distribuito in una rete esterna (perimetro/Internet)** non deve essere selezionata.
    
   - Se il server Office Web Apps è distribuito all'esterno del firewall interno, allora selezionare l'opzione **Il server Office Web Apps è distribuito in una rete esterna (perimetro/Internet)**.
    
7. Nella finestra di dialogo **Definire un nuovo server Office Web Apps** fare clic su **OK** e quindi fare clic su **OK** nella finestra di dialogo **Modifica proprietà**. L'URL di individuazione verrà quindi elencato come una delle associazioni del pool.
    
Sarà necessario ripetere questa procedura per ogni pool che deve essere associato al server Office Web Apps.
  
Dopo aver aggiunto l'URL di individuazione alla topologia, è necessario pubblicare la topologia aggiornata. Per eseguire questa operazione in Generatore di topologie:
  
1. Fare clic su **Azione** e quindi su **Pubblica topologia**.
    
2. Nella pagina **Pubblicare la topologia** della procedura guidata Pubblica topologia fare clic su **Avanti**.
    
3. Nella pagina **Pubblicazione guidata completata** fare clic su **Fine**.
    
4. Chiudere Generatore di topologie.
    
## <a name="configure-access-for-external-users"></a>Configurare l'accesso per gli utenti esterni

Se si desidera che gli utenti esterni, ovvero gli utenti che accedono dall'esterno del firewall dell'organizzazione, abbiano accesso alle presentazioni di PowerPoint del server Office Web Apps, sarà necessario utilizzare il server Office Web Apps e un server proxy inverso. È inoltre necessario creare e configurare una regola di pubblicazione del sito Web, che consentirà di verificare che gli utenti siano in grado di connettersi al server. 
  
## <a name="validate-the-configuration"></a>Convalidare la configurazione

Dopo che il server Office Web Apps è stato aggiunto alla topologia e dopo la pubblicazione della topologia, dovrebbero essere visualizzati due nuovi eventi del registro eventi nel registro eventi di Skype for Business Server. Per prima cosa, è necessario aggiungere un evento MCU dati LS (ID evento 41034). Questo evento riporterà che il server Office Web Apps è stato individuato:
  
 **Server Web Conferencing Server Office Web Apps è stato rilevato, il contenuto di PowerPoint è abilitato.**
  
Inoltre, dovrebbe essere visualizzato un altro evento LS Data MCU (ID evento 41032) che restituisce gli URL di Office Web Apps Server. Ad esempio, dovrebbe essere visualizzato un evento simile al seguente:
  
 **Individuazione del server Web Conferencing Server Office Web Apps ha avuto esito positivo.**
  
 **Pagina del relatore interno del server Office Web Apps: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp ; Embed =**
  
 **Pagina partecipante interno del server Office Web Apps: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp ; Embed = true&amp;=**
  
Se è stato configurato l'accesso per gli utenti esterni, si vedrà anche qualcosa di simile al seguente:
  
 **Pagina del relatore esterno del server Office Web Apps: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp ; incorporare**
  
 **Pagina partecipante interno del server Office Web Apps: <https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp> ;**
  
Se viene visualizzato un evento LS Data MCU con ID evento 41033, l'individuazione di Office Web Apps Server ha avuto esito negativo. In questo caso, Skype for Business Server tenterà tutte le volte che è necessario per individuare il server Office Web Apps appena configurato. Se è impossibile eseguire il processo di individuazione, è necessario rimuovere Office Web Apps Server dal documento relativo alla topologia, pubblicare la topologia aggiornata e quindi tentare di aggiungere di nuovo Office Web Apps Server alla topologia dopo avere risolto i problemi di connettività.
  
Se il server Office Web Apps sembra configurato correttamente ed è stato riconosciuto dal processo di individuazione, è possibile verificare che il server Office Web Apps funzioni come previsto condividendo una presentazione di PowerPoint tra una coppia di client Skype for business. Se l'utente A può caricare e visualizzare la presentazione di PowerPoint e l'utente B può partecipare alla riunione e visualizzare la presentazione, Office Web Apps Server funziona correttamente.
  
Anche se il server Office Web Apps sembra configurato correttamente, è possibile che venga visualizzato il messaggio di errore "alcune funzionalità di condivisione non sono disponibili a causa di problemi di connettività del server" quando si prova a condividere una presentazione di PowerPoint. Se si riceve questo messaggio di errore, riavviare i Front End Server associati al nuovo Office Web Apps Server.
  

