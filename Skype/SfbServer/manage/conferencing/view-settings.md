---
title: Visualizzare le impostazioni di configurazione delle riunioni in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: 'Riepilogo: informazioni su come visualizzare le impostazioni di configurazione delle riunioni in Skype for Business Server.'
ms.openlocfilehash: 13d91bc4c0335d8c069e0b0d9bc41efd8714f112
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188918"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a>Visualizzare le impostazioni di configurazione delle riunioni in Skype for Business Server
 
**Riepilogo:** Informazioni su come visualizzare le impostazioni di configurazione delle riunioni in Skype for Business Server.
  
Puoi visualizzare le impostazioni di configurazione delle riunioni usando il pannello di controllo di Skype for Business Server o usando Skype for Business Server Management Shell.
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Visualizzare le impostazioni di configurazione delle riunioni tramite il pannello di controllo di Skype for Business Server
<a name="BKMK_ViewJoinSettings"> </a>

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
    
2.  Aprire il pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**e quindi su **Configurazione riunione**.
    
4. Nella pagina **Configurazione riunione** fare clic sulla configurazione della riunione che si desidera visualizzare.
    
5. In **Modifica filtro file**selezionare la casella di controllo **Mostra dettagli** .
    
    **Modificare la configurazione delle \<riunioni\> :** verrà visualizzata la visualizzazione delle impostazioni per il criterio selezionato.
    
    Per informazioni dettagliate sulla configurazione delle impostazioni, vedere [creare impostazioni di configurazione delle riunioni in Skype for Business Server](create-settings.md).
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Visualizzare le impostazioni di configurazione delle riunioni con Skype for Business Server Management Shell
<a name="BKMK_ViewJoinSettings"> </a>

Per visualizzare informazioni su tutte le impostazioni di configurazione della riunione, usare il cmdlet **Get-CsMeetingConfiguration** :
  
```
Get-CsMeetingConfiguration
```

Questo comando restituirà informazioni simili a quelle seguenti:
  
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

Per altre informazioni, incluso un elenco completo dei parametri, vedere [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).
  

