---
title: Configurare l'integrazione con Office Web Apps Server in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b7e9149e-bf16-4120-afe0-3ee09c88f5eb
description: "Riepilogo: leggere questo argomento per informazioni su come configurare l'integrazione tra Office Web Apps Server e Skype for Business Server per abilitare le presentazioni di PowerPoint per i servizi di conferenza Web."
ms.openlocfilehash: b20646f31a7925ca66180c1580751574152047e5
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768349"
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server"></a>Configurare l'integrazione con Office Web Apps Server in Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per informazioni su come configurare l'integrazione tra Office Web Apps Server e Skype for Business Server per abilitare le presentazioni di PowerPoint per i servizi di conferenza Web.
  
Skype for Business Server impiega Office Web Apps Server per gestire le presentazioni di PowerPoint per i servizi di conferenza Web. Per informazioni sui vantaggi di questo approccio, vedere [pianificare le conferenze in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md).
  
Prima di poter configurare Skype for Business Server per l'uso di Office Web Apps Server, è necessario assicurarsi che Office Web Apps Server sia già distribuito e configurato. Per informazioni su Office Web Apps Server, vedere l'articolo [distribuire l'infrastruttura: server Office Online](https://go.microsoft.com/fwlink/p/?linkid=257525). 
  
Dopo l'installazione di Office Web Apps Server e la Web farm correttamente configurata, è necessario configurare Skype for Business Server per comunicare con il nuovo server aggiungendo l'URL di individuazione del server di Office Web Apps a Skype for business Topologia server. 
  
> [!NOTE]
> L'iterazione più recente di Office Web Apps Server è denominata Office Online Server, supportata da Skype for Business Server. Per altre informazioni, vedere la [documentazione del server Office Online](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx). 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a>Configurare Skype for Business Server per comunicare con Office Web Apps Server

Per aggiungere Office Web Apps Server alla topologia, eseguire la procedura seguente:
  
1. Aprire Generatore di topologia di Skype for Business Server.
    
2. Nella finestra di dialogo **Generatore di topologia** selezionare **Scarica topologia da distribuzione esistente** e quindi fare clic su **OK**.
    
3. Nella finestra di dialogo **Salva topologia come** Digitare un nome per il documento della topologia, ad esempio **PreWebAppsServerTopology**, nella casella **nome file** e quindi fare clic su **Salva**. Questa topologia può essere recuperata e ripubblicata in seguito se si verificano problemi con la nuova topologia.
    
4. In Generatore di topologie Espandi **Skype for Business Server**, Espandi il nome del sito, Espandi i **pool di front-end di Enterprise Edition**, fai clic con il pulsante destro del mouse sul nome di uno dei pool e quindi fai clic su **modifica proprietà**.
    
5. Nella scheda **generale** della finestra di dialogo **modifica proprietà** individuare il titolo **associato a Office Web Apps Server** e quindi fare clic su **nuovo** (o selezionare un server di Office Web Apps esistente nell'elenco a discesa).
    
6. Nella finestra di dialogo **Definisci nuovo server Office Web Apps** Digitare il nome di dominio completo (FQDN) del computer Office Web Apps Server nella casella **FQDN server di Office Web Apps** . Quando si esegue questa operazione, l'URL di individuazione del server di Office Web Apps deve essere automaticamente immesso nella casella **URL individuazione server di Office Web Apps** .
    
   - Se il server Office Web Apps è installato in locale e nella stessa area di rete di Skype for Business Server, l'opzione **Office Web Apps Server è distribuita in una rete esterna, ovvero perimetro/Internet,** non deve essere selezionata.
    
   - Se il server Office Web Apps è distribuito all'esterno del firewall interno, selezionare l'opzione **Office Web Apps Server è distribuito in una rete esterna (ovvero perimetro/Internet)**.
    
7. Nella finestra di dialogo **Definisci nuovo server Office Web Apps** fare clic su **OK**e quindi su **OK** nella finestra di dialogo **modifica proprietà** . L'URL di individuazione verrà quindi elencato come una delle associazioni del pool.
    
Sarà necessario ripetere questa procedura per ogni pool che deve essere associato al server Office Web Apps.
  
Dopo aver aggiunto l'URL di individuazione alla topologia, è necessario pubblicare la topologia aggiornata. Per eseguire questa operazione in Generatore di topologie:
  
1. Fare clic su **azione** e quindi su **Pubblica topologia**.
    
2. Nella pagina **Pubblica topologia** della procedura guidata Pubblica topologia fare clic su **Avanti**.
    
3. Nella pagina **completamento pubblicazione guidata** fare clic su **fine**.
    
4. Chiudi generatore di topologie.
    
## <a name="configure-access-for-external-users"></a>Configurare l'accesso per gli utenti esterni

Se si vuole che gli utenti esterni (ovvero gli utenti che accedono dall'esterno del firewall dell'organizzazione) abbiano accesso alle presentazioni di PowerPoint di Office Web Apps Server, sarà necessario usare Office Web Apps Server e un server proxy inverso. Sarà inoltre necessario creare e configurare una regola di pubblicazione del sito Web, che consentirà di verificare che gli utenti possano connettersi al server. 
  
## <a name="validate-the-configuration"></a>Convalidare la configurazione

Dopo che Office Web Apps Server è stato aggiunto alla topologia e dopo la pubblicazione di tale topologia, dovrebbero essere visualizzati due nuovi eventi del log eventi nel log eventi di Skype for Business Server. Prima di tutto, è necessario aggiungere un evento MCU dati LS (ID evento 41034); Questo evento riporterà che il server Office Web Apps è stato individuato:
  
 **Web Conferencing Server Office Web Apps Server viene individuato, il contenuto di PowerPoint è abilitato.**
  
Oltre a questo, dovrebbe essere visualizzato un altro evento di MCU dati LS (ID evento 41032) che riporta gli URL del server di Office Web Apps. Ad esempio, dovresti vedere qualcosa di simile a questo:
  
 **L'individuazione del server Web Conferencing Server Office Web Apps è riuscita.**
  
 **Pagina del relatore interno del server https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&ampOffice Web Apps:; incorporare =**
  
 **Pagina partecipanti interni a Office Web Apps Server: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp; Embed = true&amp;=**
  
Se è stato configurato l'accesso per gli utenti esterni, si vedrà anche qualcosa di simile a:
  
 **Pagina del relatore esterno del server https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&ampOffice Web Apps:; incorporare**
  
 **Pagina partecipanti interni a Office Web Apps Server: <https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp>;**
  
Se viene visualizzato un evento di MCU dati LS con l'ID evento di 41033, significa che l'individuazione di Office Web Apps Server non è riuscita. In questo caso, Skype for Business Server tenterà tutte le volte necessarie per individuare il server Office Web Apps appena configurato. Se il processo di individuazione non riesce più volte, è necessario rimuovere Office Web Apps Server dal documento della topologia, pubblicare la topologia aggiornata e quindi provare a aggiungere Office Web Apps Server alla topologia dopo la risoluzione dei problemi di connettività.
  
Se il server Office Web Apps sembra configurato correttamente ed è stato riconosciuto dal processo di individuazione, è possibile verificare che Office Web Apps Server funzioni come previsto condividendo una presentazione di PowerPoint tra una coppia di client Skype for business. Se l'utente A può caricare e visualizzare la presentazione di PowerPoint e se l'utente B può quindi partecipare alla riunione e vedere la presentazione, il server Office Web Apps funziona.
  
Anche se il server Office Web Apps sembra configurato correttamente, è possibile che venga visualizzato il messaggio di errore "alcune funzionalità di condivisione non sono disponibili a causa di problemi di connettività del server" quando si prova a condividere una presentazione di PowerPoint. Se viene visualizzato il messaggio di errore, è necessario riavviare il server front-end (o i server) associato al nuovo server Office Web Apps.
  

