---
title: Visualizzare le impostazioni di configurazione delle riunioni in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: 'Riepilogo: informazioni su come visualizzare le impostazioni di configurazione delle riunioni in Skype for Business Server.'
---

# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a>Visualizzare le impostazioni di configurazione delle riunioni in Skype for Business Server
 
**Riepilogo:** Informazioni su come visualizzare le impostazioni di configurazione delle riunioni in Skype for Business Server.
  
È possibile visualizzare le impostazioni di configurazione delle riunioni Skype for Business Server pannello di controllo o tramite Skype for Business Server Management Shell.
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Visualizzare le impostazioni di configurazione delle riunioni Skype for Business Server Pannello di controllo
<a name="BKMK_ViewJoinSettings"> </a>

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2.  Aprire Skype for Business Server Pannello di controllo.
    
3. Sulla barra di spostamento sinistra fare clic su **Conferenza** e quindi su **Configurazione riunione**.
    
4. Nella pagina **Configurazione riunione** fare clic sulla configurazione di riunione che si desidera visualizzare.
    
5. In **Modifica filtro file** selezionare la **casella di controllo** Mostra dettagli.
    
    **Modifica configurazione riunione - \<policy\>** visualizza le impostazioni per il criterio selezionato.
    
    Per informazioni dettagliate sulla configurazione delle impostazioni, vedere [Create meeting configuration settings in Skype for Business Server](create-settings.md).
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Visualizzare le impostazioni di configurazione delle riunioni tramite Skype for Business Server Management Shell
<a name="BKMK_ViewJoinSettings"> </a>

Per visualizzare informazioni su tutte le impostazioni di configurazione delle riunioni, utilizzare il cmdlet **Get-CsMeetingConfiguration** :
  
```
Get-CsMeetingConfiguration
```

Questo comando restituirà informazioni simili alle seguenti:
  
<pre>
Identity                        : Global
PstnCallersBypassLobby          : True
EnableAssignedConferenceType    : True
DesignateAsPresenter            : Company
AssignedConferenceTypeByDefault : True
AdmitAnonymousUsersByDefault    : True
RequireRoomSystemsAuthorization : False
LogoURL                         :
LegalURL                        :
HelpURL                         :
CustomFooterText                :
AllowConferenceRecording        : True
</pre>

Per ulteriori informazioni, incluso un elenco completo di parametri, [vedere Get-CsMeetingConfiguration](/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).
