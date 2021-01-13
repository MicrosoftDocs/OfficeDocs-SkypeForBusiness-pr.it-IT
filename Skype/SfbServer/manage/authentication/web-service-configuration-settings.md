---
title: Gestire le impostazioni di configurazione del servizio Web in Skype for Business Server
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
ms.collection: IT_Skype16
ms.assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
description: 'Riepilogo: gestire le impostazioni di configurazione del servizio Web in Skype for Business Server.'
ms.openlocfilehash: 68abe01614902d5e6f4c58040b30b6afbd475df8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806496"
---
# <a name="manage-web-service-configuration-settings-in-skype-for-business-server"></a>Gestire le impostazioni di configurazione del servizio Web in Skype for Business Server
 
**Riepilogo:** Gestire le impostazioni di configurazione del servizio Web in Skype for Business Server.
  
È possibile utilizzare la pagina del **servizio Web** per configurare i metodi di autenticazione per l'accesso ai server Web e ai servizi Web correlati di Skype for Business Server.
  
Eseguire la procedura seguente per creare un nuovo criterio di servizio Web.
  
### <a name="to-create-new-web-service-configuration-settings"></a>Per creare nuove impostazioni di configurazione del servizio Web

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, eseguire l'accesso a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server.
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server.  
    
3. Sulla barra di spostamento sinistra fare clic su **Sicurezza** e quindi su **Servizio Web**.
    
4. Nella pagina **servizio Web** fare clic su **nuovo** e quindi eseguire una delle operazioni seguenti:
    
   - Per configurare il servizio Web per un sito, fare clic su **configurazione sito**. In **Seleziona un sito** fare clic sul sito a cui verranno applicati i criteri del servizio Web e quindi fare clic su **OK**.
    
   - Per configurare il servizio Web per un pool, fare clic su **Configurazione pool**. In **Seleziona un servizio** fare clic sul servizio a cui verranno applicati i criteri del servizio Web e quindi fare clic su **OK**. 
    
5. In **nuova impostazione del servizio Web**, in **autenticazione integrata di Windows**, selezionare **negozia**, **autenticazione integrata di Windows** o **nessuno**.
    
6. Selezionare una o più delle opzioni seguenti in base alle capacità dei client e al supporto nell'ambiente:
    
   - **Abilita autenticazione PIN** per consentire l'autenticazione dei client tramite numeri PIN.
    
   - **Abilita autenticazione certificato** per fare in modo che i server nel pool emettano i certificati per i client.
    
   - **Abilita download catena di certificati** per fare in modo che i server a cui viene presentato un certificato di autenticazione eseguano il download della catena di certificati per tale certificato.
    
7. Fare clic su **Commit**.
    
## <a name="modify-existing-web-service-configuration-settings"></a>Modificare le impostazioni di configurazione del servizio Web esistenti

È possibile utilizzare la pagina del **servizio Web** per configurare i metodi di autenticazione per l'accesso ai server Web e ai servizi Web correlati di Skype for Business Server.
  
Eseguire la procedura seguente per modificare i criteri per un servizio Web esistente.
  
### <a name="to-modify-existing-web-service-configuration-settings"></a>Per modificare le impostazioni di configurazione del servizio Web esistenti

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, eseguire l'accesso a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server.
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server.  
    
3. Sulla barra di spostamento sinistra fare clic su **Sicurezza** e quindi su **Servizio Web**.
    
4. Nella pagina **Servizio Web** fare clic su una configurazione, fare clic su **Modifica** e quindi su **Mostra dettagli**.
    
5. In **Modifica impostazione servizio Web**, in **Autenticazione integrata di Windows**, selezionare **Negoziazione**, **Autenticazione integrata di Windows** o **Nessuno**.
    
6. Selezionare una o più delle opzioni seguenti in base alle capacità dei client e al supporto nell'ambiente:
    
   - **Abilita autenticazione PIN** per consentire l'autenticazione dei client tramite numeri PIN.
    
   - **Abilita autenticazione certificato** per fare in modo che i server nel pool emettano i certificati per i client.
    
   - **Abilita download catena di certificati** per fare in modo che i server a cui viene presentato un certificato di autenticazione eseguano il download della catena di certificati per tale certificato.
    
7. Fare clic su **Commit**.
    
## <a name="delete-existing-web-service-configuration-settings"></a>Eliminare le impostazioni di configurazione del servizio Web esistenti

Eseguire la procedura seguente per eliminare le impostazioni di configurazione del servizio Web.
  
### <a name="to-delete-web-service-configuration-settings"></a>Per eliminare le impostazioni di configurazione del servizio Web

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, eseguire l'accesso a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server.
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server.  
    
3. Sulla barra di spostamento sinistra fare clic su **Sicurezza** e quindi su **Servizio Web**.
    
4. Nella pagina **Servizio Web** digitare il nome dei criteri che si desidera eliminare nel campo di ricerca, per intero o in parte.
    
5. Nell'elenco dei criteri fare clic sui criteri desiderati, fare clic su **Modifica** e quindi su **Elimina**.
    
6. Fare clic su **OK**.
    
## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a>Eliminazione delle impostazioni di configurazione del servizio Web tramite i cmdlet di Windows PowerShell

È possibile eliminare le impostazioni di configurazione del servizio Web utilizzando Windows PowerShell e il cmdlet **Remove-CsWebServiceConfiguration** . È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo del Blog ["Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Il processo è lo stesso in Skype for Business Server.
  
### <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a>Per eliminare una raccolta specifica di impostazioni di configurazione di servizi Web

- Con il comando seguente vengono rimosse le impostazioni di sicurezza di servizi Web applicate al sito Redmond:
    
  ```PowerShell
  Remove-CsWebServiceConfiguration -Identity "site:Redmond"
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a>Per eliminare tutte le impostazioni di configurazione del servizio Web applicate all'ambito del sito

Con il comando seguente vengono rimosse tutte le impostazioni di sicurezza di servizi Web applicate nell'ambito del servizio:
    
  ```PowerShell
  Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a>Per eliminare tutte le impostazioni di configurazione del servizio Web che consentono l'autenticazione dei certificati

Con il comando seguente vengono rimosse tutte le impostazioni di sicurezza di servizi Web che consentono l'utilizzo dell'autenticazione basata sui certificati:
    
  ```PowerShell
  Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration
  ```

Per informazioni dettagliate, vedere [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).
  

