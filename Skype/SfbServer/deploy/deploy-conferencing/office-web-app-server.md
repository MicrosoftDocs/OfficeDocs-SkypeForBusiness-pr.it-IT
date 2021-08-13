---
title: Configurare l'integrazione con Office Web Apps Server in Skype for Business Server
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
description: "Riepilogo: leggere questo argomento per informazioni su come configurare l'integrazione tra Office Web Apps Server e Skype for Business Server per abilitare le presentazioni PowerPoint per le conferenze Web."
ms.openlocfilehash: abaf430ffd2f426d8ed4821409691cc140bb9fa8fe3dd0e23bcf10cbc444c33b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54338784"
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server"></a>Configurare l'integrazione con Office Web Apps Server in Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per informazioni su come configurare l'integrazione tra Office Web Apps Server e Skype for Business Server per abilitare PowerPoint presentazioni per conferenze Web.
  
Skype for Business Server si avvale Office Web Apps Server per gestire PowerPoint presentazioni per conferenze Web. Per informazioni sui vantaggi di questo approccio, vedere [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md).
  
Prima di poter configurare Skype for Business Server per l'utilizzo di Office Web Apps Server, è necessario verificare che Office Web Apps Server sia già distribuito e configurato. Per informazioni su Office Server Web Apps, vedere l'articolo [Distribuire l'infrastruttura: Office Online Server](/webappsserver/deploy-the-infrastructure-office-web-apps-server). 
  
Dopo aver installato correttamente Office Web Apps Server e aver configurato correttamente la Web farm, è necessario configurare Skype for Business Server per comunicare con il nuovo server aggiungendo l'URL di individuazione del server app Web Office alla topologia di Skype for Business Server. 
  
> [!NOTE]
> L'iterazione più recente Office Web Apps Server è denominata Office Online Server, supportata da Skype for Business Server. Per ulteriori dettagli, fare riferimento alla documentazione [Office Online Server .](/officeonlineserver/office-online-server) 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a>Configurare Skype for Business Server per comunicare con Office Web Apps Server

Per aggiungere il server Office Web Apps alla topologia, eseguire le operazioni seguenti:
  
1. Aprire Skype for Business Server Generatore di topologie.
    
2. Nella finestra di dialogo **Generatore di topologie** selezionare **Scarica topologia dalla distribuzione esistente** e quindi fare clic su **OK**.
    
3. Nella casella **Salva topologia con nome** digitare un nome per il documento della topologia (ad esempio **TopologiaPreServerWebApps**) nella casella **Nome file** e quindi fare clic su **Salva**. Questa topologia potrà essere recuperata e ripubblicata in seguito se si verificano problemi con la nuova topologia.
    
4. In Generatore di topologie **espandere Skype for Business Server**, espandere il nome del **sito,** espandere edizione Enterprise Pool Front End , fare clic con il pulsante destro del mouse sul nome di uno dei pool e quindi scegliere **Modifica proprietà**.
    
5. Nella scheda **Generale** della finestra di dialogo **Modifica proprietà** individuare il titolo **Associa il pool a un server Office Web Apps** e quindi fare clic su **Nuovo** oppure selezionare un server Office Web Apps esistente nell'elenco a discesa.
    
6. Nella finestra di dialogo **Definire un nuovo server Office Web Apps** digitare il nome di dominio completo (FQDN) del computer del server Office Web Apps nella casella **FQDN server Office Web Apps**. L'URL di individuazione del server Office Web Apps dovrebbe comparire così automaticamente nella casella **URL di individuazione server Office Web Apps**.
    
   - Se il server Office Web Apps è installato in locale e nella stessa area di rete di Skype for Business Server, l'opzione Office Web Apps Server viene distribuita in una rete esterna, ovvero **perimetro/Internet,** non deve essere selezionata.
    
   - Se il server Office Web Apps è distribuito all'esterno del firewall interno, allora selezionare l'opzione **Il server Office Web Apps è distribuito in una rete esterna (perimetro/Internet)**.
    
7. Nella finestra di dialogo **Definire un nuovo server Office Web Apps** fare clic su **OK** e quindi fare clic su **OK** nella finestra di dialogo **Modifica proprietà**. L'URL di individuazione verrà quindi elencato come una delle associazioni del pool.
    
Sarà necessario ripetere questa procedura per ogni pool che deve essere associato al server Office Web Apps.
  
Dopo aver aggiunto l'URL di individuazione alla topologia, è necessario pubblicare la topologia aggiornata. A tale scopo, in Generatore di topologie:
  
1. Fare clic su **Azione** e quindi su **Pubblica topologia**.
    
2. Nella pagina **Pubblicare la topologia** della procedura guidata Pubblica topologia fare clic su **Avanti**.
    
3. Nella pagina **Pubblicazione guidata completata** fare clic su **Fine**.
    
4. Chiudere Generatore di topologie.
    
## <a name="configure-access-for-external-users"></a>Configurare l'accesso per gli utenti esterni

Se si desidera che gli utenti esterni, ovvero gli utenti che accedono dall'esterno del firewall dell'organizzazione, abbiano accesso alle presentazioni di Office Web Apps Server PowerPoint, sarà necessario utilizzare Office Web Apps Server e un server proxy inverso. Sarà inoltre necessario creare e configurare una regola di pubblicazione del sito Web, in modo da garantire che gli utenti siano in grado di connettersi al server. 
  
## <a name="validate-the-configuration"></a>Convalidare la configurazione

Dopo Office server Web Apps è stato aggiunto alla topologia e dopo che tale topologia è stata pubblicata, nel registro eventi di Skype for Business Server dovrebbero essere visualizzati due nuovi eventi del registro eventi. Innanzitutto, deve essere aggiunto un evento LS Data MCU (ID evento 41034). questo evento segnala che il Office Web Apps Server è stato individuato:
  
 **Web Conferencing Server Office Web Apps Server viene individuato e PowerPoint contenuto è abilitato.**
  
Inoltre, dovrebbe essere visualizzato un altro evento LS Data MCU (ID evento 41032) che restituisce gli URL di Office Web Apps Server. Ad esempio, dovrebbe essere visualizzato un evento simile al seguente:
  
 **L'individuazione di Web Conferencing Server Office Web Apps Server è riuscita.**
  
 **Office Pagina del relatore interno del server Web Apps: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp ;embed=**
  
 **Office Pagina partecipante interno del server Web Apps: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp ;embed=true&amp;=**
  
Se è stato configurato l'accesso per gli utenti esterni, verrà visualizzato anche un elemento simile al seguente:
  
 **Office Pagina del relatore esterno del server Web Apps: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp ;embed**
  
 **Office Pagina partecipante interno del server Web Apps: <https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp> ;**
  
Se viene visualizzato un evento LS Data MCU con ID evento 41033, l'individuazione di Office Web Apps Server ha avuto esito negativo. In questo caso, Skype for Business Server il numero di volte necessario per individuare il nuovo server Office Web Apps. Se è impossibile eseguire il processo di individuazione, è necessario rimuovere Office Web Apps Server dal documento relativo alla topologia, pubblicare la topologia aggiornata e quindi tentare di aggiungere di nuovo Office Web Apps Server alla topologia dopo avere risolto i problemi di connettività.
  
Se Office Web Apps Server sembra essere configurato correttamente ed è stato riconosciuto dal processo di individuazione, è possibile verificare che Office Web Apps Server funzioni come previsto condividendo una presentazione di PowerPoint tra due client Skype for Business. Se l'utente A può caricare e visualizzare la presentazione di PowerPoint e l'utente B può partecipare alla riunione e visualizzare la presentazione, Office Web Apps Server funziona correttamente.
  
Anche se Office Web Apps Server sembra essere configurato correttamente, è possibile che venga visualizzato il messaggio di errore "Alcune funzionalità di condivisione non sono disponibili a causa di problemi di connettività del server" quando si tenta di condividere una presentazione di PowerPoint. Se si riceve questo messaggio di errore, riavviare i Front End Server associati al nuovo Office Web Apps Server.
