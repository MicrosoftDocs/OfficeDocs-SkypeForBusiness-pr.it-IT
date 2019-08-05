---
title: Configurare criteri per controllare l'accesso utente federato
ms.reviewer: ''
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Quando si configurano i criteri per supportare le comunicazioni con partner federati, i criteri si applicano agli utenti di domini federati. '
ms.openlocfilehash: 00552dfd6e2cb92d1bd50cb851bfb8324122c5ff
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188852"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a>Configurare i criteri per controllare l'accesso degli utenti federati in Skype for Business Server

Quando si configurano i criteri per supportare le comunicazioni con partner federati, i criteri si applicano agli utenti di domini federati. Puoi configurare uno o più criteri di accesso utenti esterni per controllare se gli utenti di domini federati possono collaborare con gli utenti di Skype for Business Server. Per controllare l'accesso degli utenti federati, è possibile configurare i criteri a livello globale, sito e utente. Le impostazioni dei criteri di Skype for Business Server applicate a un livello di criteri possono eseguire l'override delle impostazioni applicate a un altro livello di criteri. La precedenza dei criteri di Skype for Business Server è: criteri utente (la maggior parte delle influenze) esegue l'override di un criterio del sito e quindi un criterio del sito sostituisce un criterio globale (almeno l'influenza). Ciò significa che l'impostazione del criterio è più vicina all'oggetto che il criterio sta influenzando, più influenza ha sull'oggetto.


> [!NOTE]  
> È possibile configurare i criteri per controllare l'accesso degli utenti federati, anche se non è stata abilitata la Federazione per l'organizzazione. Tuttavia, i criteri configurati sono attivi solo quando è abilitata la Federazione per l'organizzazione. Per informazioni dettagliate sull'abilitazione della Federazione, vedere [abilitare o disabilitare l'accesso remoto agli utenti](../access-edge/enable-or-disable-remote-user-access.md).  Inoltre, se specifichi un criterio utente per controllare l'accesso degli utenti federati, il criterio si applica solo agli utenti abilitati per Skype for Business Server e configurati per l'uso dei criteri.


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a>Per configurare un criterio per il supporto dell'accesso da parte di utenti di domini federati

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.

3.  Sulla barra di spostamento sinistra fare clic su **accesso utente esterno**e quindi su **criteri di accesso esterno**.

4.  Nella pagina **criteri di accesso esterno** eseguire una delle operazioni seguenti:
    
      - Per configurare il criterio globale per il supporto dell'accesso degli utenti federati, fare clic sul criterio globale, fare clic su **modifica**e quindi su **Mostra dettagli**.
    
      - Per creare un nuovo criterio sito, fare clic su **nuovo**e quindi su **criteri sito**. In **Seleziona un sito**fare clic sul sito appropriato nell'elenco e quindi fare clic su **OK**.
    
      - Per creare un nuovo criterio utente, fare clic su **nuovo**e quindi su **criteri utente**. In **nuovi criteri di accesso esterno**, creare un nome univoco nel campo **nome** che indichi le informazioni relative ai criteri utente, ad esempio **EnableFederatedUsers** , per un criterio utente che consente le comunicazioni per gli utenti di domini federati.
    
      - Per modificare un criterio esistente, fare clic sul criterio appropriato elencato nella tabella, fare clic su **modifica**e quindi su **Mostra dettagli**.

5.  Opzionale Se si vuole aggiungere o modificare una descrizione, specificare le informazioni per il criterio in **Descrizione**.

6.  Esegui una delle operazioni seguenti:
    
      - Per abilitare l'accesso degli utenti federati per il criterio, selezionare la casella di controllo **Abilita comunicazioni con gli utenti federati** .
    
      - Per disabilitare l'accesso degli utenti federati per il criterio, deselezionare la casella di controllo **Abilita comunicazioni con gli utenti federati** .

7.  Fare clic su **Commit**.

Per abilitare l'accesso degli utenti federati, devi anche abilitare il supporto per la Federazione nell'organizzazione. Per informazioni dettagliate, vedere [abilitare o disabilitare la connettività per la messaggistica istantanea pubblica e la Federazione](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).

Se si tratta di un criterio utente, devi anche applicare il criterio agli utenti che vuoi collaborare con gli utenti federati. Per informazioni dettagliate, vedere [assegnare criteri di accesso degli utenti esterni](assign-an-external-user-access-policy.md).

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Per configurare un criterio esistente con Windows PowerShell per supportare l'accesso da parte di utenti di domini federati

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Avviare Skype for busines Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for Business Server**e quindi su **Skype for Business Server Management Shell**.

3.  Digitare quanto segue in Skype for Business Server Management Shell:
    
    ```
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > Il parametro "EnablePublicCloudAudioVideoAccess" non ha una selezione corrispondente nel pannello di controllo di Skype for Business Server


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Per creare un nuovo criterio usando Windows PowerShell per supportare l'accesso da parte di utenti di domini federati

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Microsoft Skype for business**server e quindi su **Skype for Business Server Management Shell**.

3.  Digitare quanto segue in Skype for Business Server Management Shell:
    
    ```
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    Esempio di creazione di un nuovo criterio di sito:
    
    ```
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Per eliminare o reimpostare un criterio con Windows PowerShell per supportare l'accesso da parte di utenti di domini federati

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Digitare quanto segue in Skype for Business Server Management Shell
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    Esempio di reimpostazione del criterio globale (il criterio globale può avere solo l'impostazione rimossa. Non è possibile eliminare i criteri:
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    Per rimuovere un criterio sito, digitare:
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    Elimina i criteri del sito Redmond. Per eliminare un criterio utente denominato UserEAPPolicy, digitare:
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a>Vedere anche


[Abilitare o disabilitare la federazione e la connettività per la messaggistica istantanea pubblica](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[Assegnare un criterio di accesso utente esterno](assign-an-external-user-access-policy.md)

[Gestire i domini federati SIP per l'organizzazione](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[Gestire i provider federati SIP per l'organizzazione](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[Set-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy)  
[New-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

