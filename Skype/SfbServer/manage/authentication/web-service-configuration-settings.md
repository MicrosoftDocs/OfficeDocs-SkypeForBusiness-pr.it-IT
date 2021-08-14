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
ms.openlocfilehash: a4fb1474655e695f030180a7345375ef1a1e53e3aaadad18167ed7d41d3a9864
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54328161"
---
# <a name="manage-web-service-configuration-settings-in-skype-for-business-server"></a>Gestire le impostazioni di configurazione del servizio Web in Skype for Business Server
 
**Riepilogo:** Gestire le impostazioni di configurazione del servizio Web in Skype for Business Server.
  
È possibile utilizzare la **pagina Servizio Web** per configurare i metodi di autenticazione per Skype for Business Server server Web e servizi Web correlati.
  
Seguire questa procedura per creare un nuovo criterio servizio Web.
  
### <a name="to-create-new-web-service-configuration-settings"></a>Per creare nuove impostazioni di configurazione del servizio Web

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer nella rete in cui è stato distribuito Skype for Business Server.
    
2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo.  
    
3. Sulla barra di spostamento sinistra fare clic su **Sicurezza** e quindi su **Servizio Web**.
    
4. Nella pagina **Servizio Web** fare clic su **Nuovo** e quindi eseguire una delle operazioni seguenti:
    
   - Per configurare il servizio Web per un sito, fare clic su **Configurazione sito.** In **Selezionare un sito** fare clic sul sito a cui verrà applicato il criterio Servizio Web e quindi fare clic su **OK.**
    
   - Per configurare il servizio Web per un pool, fare clic su **Configurazione pool.** In **Selezionare un servizio** fare clic sul servizio a cui verrà applicato il criterio servizio Web e fare clic su **OK.** 
    
5. In **Nuova impostazione servizio Web,** in Autenticazione **Windows**, selezionare Negozia **,** Autenticazione **Windows** integrata o **Nessuna**.
    
6. Selezionare una o più delle opzioni seguenti in base alle capacità dei client e al supporto nell'ambiente:
    
   - **Abilita autenticazione PIN** per consentire l'autenticazione dei client tramite numeri PIN.
    
   - **Abilita autenticazione certificato** per fare in modo che i server nel pool emettano i certificati per i client.
    
   - **Abilita download catena di certificati** per fare in modo che i server a cui viene presentato un certificato di autenticazione eseguano il download della catena di certificati per tale certificato.
    
7. Fare clic su **Commit**.
    
## <a name="modify-existing-web-service-configuration-settings"></a>Modificare le impostazioni di configurazione del servizio Web esistenti

È possibile utilizzare la **pagina Servizio Web** per configurare i metodi di autenticazione per Skype for Business Server server Web e servizi Web correlati.
  
Eseguire la procedura seguente per modificare i criteri per un servizio Web esistente.
  
### <a name="to-modify-existing-web-service-configuration-settings"></a>Per modificare le impostazioni di configurazione del servizio Web esistenti

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer nella rete in cui è stato distribuito Skype for Business Server.
    
2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo.  
    
3. Sulla barra di spostamento sinistra fare clic su **Sicurezza** e quindi su **Servizio Web**.
    
4. Nella pagina **Servizio Web** fare clic su una configurazione, fare clic su **Modifica** e quindi su **Mostra dettagli**.
    
5. In **Modifica impostazione servizio Web**, in **Autenticazione integrata di Windows**, selezionare **Negoziazione**, **Autenticazione integrata di Windows** o **Nessuno**.
    
6. Selezionare una o più delle opzioni seguenti in base alle capacità dei client e al supporto nell'ambiente:
    
   - **Abilita autenticazione PIN** per consentire l'autenticazione dei client tramite numeri PIN.
    
   - **Abilita autenticazione certificato** per fare in modo che i server nel pool emettano i certificati per i client.
    
   - **Abilita download catena di certificati** per fare in modo che i server a cui viene presentato un certificato di autenticazione eseguano il download della catena di certificati per tale certificato.
    
7. Fare clic su **Commit**.
    
## <a name="delete-existing-web-service-configuration-settings"></a>Eliminare le impostazioni di configurazione del servizio Web esistenti

Seguire questa procedura per eliminare le impostazioni di configurazione del servizio Web.
  
### <a name="to-delete-web-service-configuration-settings"></a>Per eliminare le impostazioni di configurazione del servizio Web

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer nella rete in cui è stato distribuito Skype for Business Server.
    
2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo.  
    
3. Sulla barra di spostamento sinistra fare clic su **Sicurezza** e quindi su **Servizio Web**.
    
4. Nella pagina **Servizio Web** digitare il nome dei criteri che si desidera eliminare nel campo di ricerca, per intero o in parte.
    
5. Nell'elenco dei criteri fare clic sui criteri desiderati, fare clic su **Modifica** e quindi su **Elimina**.
    
6. Fare clic su **OK**.
    
## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a>Eliminazione di Impostazioni di configurazione del servizio Web tramite Windows PowerShell cmdlet

È possibile eliminare le impostazioni di configurazione del servizio Web utilizzando Windows PowerShell e il cmdlet **Remove-CsWebServiceConfiguration.** È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'Windows PowerShell per connettersi a Skype for Business Server, vedere l'articolo del blog ["Guida introduttiva: Gestione di Microsoft Lync Server 2010 tramite Remote PowerShell".](https://go.microsoft.com/fwlink/p/?linkId=255876) Il processo è lo stesso in Skype for Business Server.
  
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

### <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a>Per eliminare tutte le impostazioni di configurazione del servizio Web che consentono l'autenticazione del certificato

Con il comando seguente vengono rimosse tutte le impostazioni di sicurezza di servizi Web che consentono l'utilizzo dell'autenticazione basata sui certificati:
    
  ```PowerShell
  Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration
  ```

Per informazioni dettagliate, [vedere Remove-CsWebServiceConfiguration.](/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps)
