---
title: "Lync Server 2013: Configurare criteri per controllare l'accesso utente federato"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control federated user access
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1aeb1b29637fd3f4a8add770470069e8b4a6eb8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763288"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-federated-user-access-in-lync-server-2013"></a>Configurare criteri per controllare l'accesso utente federato in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-02-05_

Quando si configurano i criteri per supportare le comunicazioni con partner federati, i criteri si applicano agli utenti di domini federati. Puoi configurare uno o più criteri di accesso utenti esterni per controllare se gli utenti di domini federati possono collaborare con gli utenti di Lync Server 2013. Per controllare l'accesso degli utenti federati, è possibile configurare i criteri a livello globale, sito e utente. Le impostazioni dei criteri di Lync Server applicate a un livello di criteri possono eseguire l'override delle impostazioni applicate a un altro livello di criteri. La precedenza dei criteri di Lync Server è: criteri utente (la maggior parte delle influenze) esegue l'override di un criterio del sito e quindi un criterio del sito sostituisce un criterio globale (almeno l'influenza). Ciò significa che l'impostazione del criterio è più vicina all'oggetto che il criterio sta influenzando, più influenza ha sull'oggetto.

<div>


> [!NOTE]  
> È possibile configurare i criteri per controllare l'accesso degli utenti federati, anche se non è stata abilitata la Federazione per l'organizzazione. Tuttavia, i criteri configurati sono attivi solo quando è abilitata la Federazione per l'organizzazione. Per informazioni dettagliate sull'abilitazione della Federazione, vedere <A href="lync-server-2013-enable-or-disable-remote-user-access.md">abilitare o disabilitare l'accesso remoto agli utenti in Lync Server 2013</A> nella documentazione relativa alla distribuzione o nella documentazione delle operazioni. Inoltre, se specifichi un criterio utente per controllare l'accesso degli utenti federati, il criterio si applica solo agli utenti abilitati per Lync Server 2013 e configurati per l'uso dei criteri.



</div>

<div>

## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a>Per configurare un criterio per il supporto dell'accesso da parte di utenti di domini federati

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

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

Per abilitare l'accesso degli utenti federati, devi anche abilitare il supporto per la Federazione nell'organizzazione. Per informazioni dettagliate, vedere [abilitare o disabilitare la connettività per la messaggistica istantanea pubblica e la Federazione in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md).

Se si tratta di un criterio utente, devi anche applicare il criterio agli utenti che vuoi collaborare con gli utenti federati. Per informazioni dettagliate, vedere [assegnare criteri di accesso degli utenti esterni a un utente abilitato a Lync in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md).

</div>

<div>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Per configurare un criterio esistente con Windows PowerShell per supportare l'accesso da parte di utenti di domini federati

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Digitare quanto segue in Lync Server Management Shell:
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    Un comando di esempio che imposterà il criterio globale per l'accesso degli utenti federati all'accesso abilitato al dominio XMPP a abilitato, accesso remoto agli utenti abilitati, accesso del provider pubblico abilitato e concedere la possibilità di usare l'audio e il video per i provider pubblici che la supportano:
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    
    <div>
    

    > [!TIP]  
    > Il parametro "EnablePublicCloudAudioVideoAccess" non ha una selezione corrispondente nel pannello di controllo di Lync Server

    
    </div>

</div>

<div>

## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Per creare un nuovo criterio usando Windows PowerShell per supportare l'accesso da parte di utenti di domini federati

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Digitare quanto segue in Lync Server Management Shell:
    
        New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    Esempio di creazione di un nuovo criterio di sito:
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true

</div>

<div>

## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Per eliminare o reimpostare un criterio con Windows PowerShell per supportare l'accesso da parte di utenti di domini federati

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Digitare quanto segue in Lync Server Management Shell
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy> 
    
    Esempio di reimpostazione del criterio globale (il criterio globale può avere solo l'impostazione rimossa. Non è possibile eliminare i criteri:
    
        Remove-CsExternalAccessPolicy -Identity global 
    
    Per rimuovere un criterio sito, digitare:
    
        Remove-CsExternalAccessPolicy -Identity site:Redmond 
    
    Elimina i criteri del sito Redmond. Per eliminare un criterio utente denominato UserEAPPolicy, digitare:
    
        Remove-CsExternalAccessPolicy -Identity UserEAPPolicy

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Abilitare o disabilitare la federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
[Assegnare criteri di accesso per gli utenti esterni a un utente abilitato per Lync in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  


[Gestire i domini federati SIP per l'organizzazione in Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[Gestire i provider federati SIP per l'organizzazione in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
[Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[New-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

