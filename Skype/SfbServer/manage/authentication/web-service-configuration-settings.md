---
title: Gestire le impostazioni di configurazione dei servizi Web in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
description: 'Riepilogo: gestire le impostazioni di configurazione dei servizi Web in Skype for Business Server.'
ms.openlocfilehash: b2a7f287c9386c89d132e03e96aa25e9472f7008
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194952"
---
# <a name="manage-web-service-configuration-settings-in-skype-for-business-server"></a>Gestire le impostazioni di configurazione dei servizi Web in Skype for Business Server
 
**Riepilogo:** Gestire le impostazioni di configurazione dei servizi Web in Skype for Business Server.
  
È possibile usare la pagina del **servizio Web** per configurare i metodi di autenticazione per l'accesso ai server Web e ai servizi Web correlati a Skype for Business Server.
  
Seguire questa procedura per creare un nuovo criterio di servizio Web.
  
### <a name="to-create-new-web-service-configuration-settings"></a>Per creare nuove impostazioni di configurazione del servizio Web

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. .
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.  
    
3. Sulla barra di spostamento sinistra fare clic su **sicurezza** e quindi su **servizio Web**.
    
4. Nella pagina **servizio Web** fare clic su **nuovo**e quindi eseguire una delle operazioni seguenti:
    
   - Per configurare il servizio Web per un sito, fare clic su **configurazione sito**. In **Seleziona un sito**fare clic sul sito a cui verranno applicati i criteri di servizio Web e fare clic su **OK**.
    
   - Per configurare il servizio Web per un pool, fare clic su **Configurazione pool**. In **Seleziona un servizio**fare clic sul servizio a cui verranno applicati i criteri di servizio Web e fare clic su **OK**. 
    
5. Nell' **impostazione di un nuovo servizio Web**, nell' **autenticazione integrata di Windows**, selezionare **negozia**, **autenticazione di Windows integrata**o **nessuno**.
    
6. Selezionare una o più delle opzioni seguenti in base alle funzionalità dei client e al supporto nell'ambiente:
    
   - **Abilitare l'autenticazione PIN** per consentire ai client di essere autenticati usando i numeri di pin.
    
   - **Abilitare l'autenticazione del certificato** affinché i server del pool rilasciano certificati ai client.
    
   - **Abilitare il download della catena di certificati per consentire** ai server presentati con un certificato di autenticazione di scaricare la catena di certificati per tale certificato.
    
7. Fare clic su **Commit**.
    
## <a name="modify-existing-web-service-configuration-settings"></a>Modificare le impostazioni di configurazione del servizio Web esistente

È possibile usare la pagina del **servizio Web** per configurare i metodi di autenticazione per l'accesso ai server Web e ai servizi Web correlati a Skype for Business Server.
  
Seguire questa procedura per modificare un criterio di servizio Web esistente.
  
### <a name="to-modify-existing-web-service-configuration-settings"></a>Per modificare le impostazioni di configurazione del servizio Web esistente

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. .
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.  
    
3. Sulla barra di spostamento sinistra fare clic su **sicurezza** e quindi su **servizio Web**.
    
4. Nella pagina **servizio Web** fare clic su una configurazione, fare clic su **modifica**e quindi su **Mostra dettagli**.
    
5. In **Modifica impostazione servizio Web**, in **autenticazione di Windows integrata**, selezionare **negozia**, **autenticazione di Windows integrata**o **nessuno**.
    
6. Selezionare una o più delle opzioni seguenti in base alle funzionalità dei client e al supporto nell'ambiente:
    
   - **Abilitare l'autenticazione PIN** per consentire ai client di essere autenticati usando i numeri di pin.
    
   - **Abilitare l'autenticazione del certificato** affinché i server del pool rilasciano certificati ai client.
    
   - **Abilitare il download della catena di certificati per consentire** ai server presentati con un certificato di autenticazione di scaricare la catena di certificati per tale certificato.
    
7. Fare clic su **Commit**.
    
## <a name="delete-existing-web-service-configuration-settings"></a>Eliminare le impostazioni di configurazione del servizio Web esistenti

Seguire questa procedura per eliminare le impostazioni di configurazione del servizio Web.
  
### <a name="to-delete-web-service-configuration-settings"></a>Per eliminare le impostazioni di configurazione del servizio Web

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. .
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.  
    
3. Sulla barra di spostamento sinistra fare clic su **sicurezza** e quindi su **servizio Web**.
    
4. Nella pagina **servizio Web** e nel campo di ricerca digitare tutto o parte del nome del criterio che si desidera eliminare.
    
5. Nell'elenco dei criteri fare clic sui criteri desiderati, fare clic su **modifica**e quindi su **Elimina**.
    
6. Fare clic su **OK**.
    
## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a>Eliminazione delle impostazioni di configurazione del servizio Web tramite i cmdlet di Windows PowerShell

Per eliminare le impostazioni di configurazione del servizio Web, è possibile usare Windows PowerShell e il cmdlet **Remove-CsWebServiceConfiguration** . Puoi eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo di Blog ["Guida introduttiva: gestione di Microsoft Lync Server 2010 con Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Il processo è lo stesso in Skype for Business Server.
  
### <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a>Per eliminare una raccolta specifica di impostazioni di configurazione del servizio Web

- Il comando seguente rimuove le impostazioni di sicurezza del servizio Web applicate al sito Redmond:
    
  ```
  Remove-CsWebServiceConfiguration -Identity "site:Redmond"
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a>Per eliminare tutte le impostazioni di configurazione del servizio Web applicate all'ambito del sito

Il comando seguente rimuove tutte le impostazioni di sicurezza del servizio Web applicate all'ambito del servizio:
    
  ```
  Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a>Per eliminare tutte le impostazioni di configurazione del servizio Web che consentono l'autenticazione dei certificati

Il comando seguente rimuove tutte le impostazioni di sicurezza del servizio Web che consentono l'uso dell'autenticazione dei certificati:
    
  ```
  Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration
  ```

Per informazioni dettagliate, vedere [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).
  

