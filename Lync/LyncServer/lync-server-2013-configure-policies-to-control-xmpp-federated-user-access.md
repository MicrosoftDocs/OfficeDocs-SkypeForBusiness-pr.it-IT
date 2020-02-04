---
title: "Lync Server 2013: Configurare criteri per controllare l'accesso utente federato XMPP"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control XMPP federated user access
ms:assetid: 0fe0ff75-e52a-4e3e-923a-64f6412ac4e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552446(v=OCS.15)
ms:contentKeyID: 48679557
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc79a915d0735f87c0852dff0ba4228b1e391fd8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730031"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-xmpp-federated-user-access-in-lync-server-2013"></a>Configurare criteri per controllare l'accesso utente federato XMPP in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Questa è la documentazione preliminare ed è soggetta a modifiche. Gli argomenti vuoti sono inclusi come segnaposto.

Quando si configurano i criteri per il supporto dei partner federati di Extensible Messaging and Presence Protocol (XMPP), i criteri si applicano agli utenti di domini federati XMPP, ma non agli utenti dei provider di servizi di messaggistica istantanea SIP (Session Initiation Protocol) (ad esempio, Windows Live) o i domini federati SIP. Si configura un **partner federato XMPP** per ogni dominio federato XMPP in cui si vuole consentire agli utenti di aggiungere contatti e comunicare. I criteri dei partner federati XMPP sono disponibili solo in un unico ambito, anche se non sono definiti come criteri globali, agiscono come criteri globali. Per definire un criterio globale, del sito o dell'utente per i partner federativi XMPP, è possibile configurare l'ambito dei criteri creando e configurando i criteri di accesso esterno per l'ambito richiesto. Per informazioni dettagliate sui tipi di criteri che è possibile configurare per l'accesso esterno e la Federazione, vedere [gestione della Federazione e accesso esterno a Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) nella documentazione delle operazioni.

<div>


> [!NOTE]  
> Tutti i criteri di <STRONG>Federazione e di accesso esterno</STRONG> vengono applicati tramite il provisioning in banda. I criteri che si applicano all'utente, appartengono a un sito oppure l'ambito globale viene comunicato al client durante l'accesso. È possibile configurare i criteri per il controllo dell'accesso dei partner federati XMPP, anche se non è stata abilitata la Federazione XMPP per l'organizzazione. Tuttavia, i criteri configurati hanno effetto solo quando la Federazione partner XMPP è stata distribuita, abilitata e configurata per l'organizzazione. Per informazioni dettagliate sulla distribuzione e configurazione della Federazione partner XMPP, vedere Configurazione della federazione <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">SIP, della Federazione XMPP e della messaggistica istantanea pubblica in Lync Server 2013</A> nella documentazione relativa alla distribuzione. Inoltre, se specifichi un criterio utente in criteri di accesso esterno per controllare i partner federativi XMPP, il criterio si applica solo agli utenti abilitati per Lync Server 2013 e configurati per l'uso dei criteri.



</div>

<div>

## <a name="to-edit-a-global-policy-for-xmpp-federated-partners"></a>Per modificare un criterio globale per i partner federati XMPP

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **accesso utente esterno**e quindi su **criteri di accesso esterno**.

4.  Nella pagina **criteri di accesso esterno** eseguire le operazioni seguenti per il criterio globale:

5.  Fare clic sul criterio globale, scegliere **modifica**e quindi fare clic su Mostra dettagli.

6.  Specificare una descrizione per il criterio globale (facoltativo).

7.  Selezionare **Abilita comunicazioni con gli utenti federati**.

8.  Selezionare **Abilita comunicazioni con utenti federati XMPP**.

9.  Fare clic su **conferma** per salvare le modifiche apportate al criterio globale.

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners"></a>Per creare un sito o un criterio utente per partner federati XMPP

1.  Fare clic su **nuovo**e quindi su criteri **sito** o **criteri utente**. In **Seleziona un sito**fare clic sul sito appropriato nell'elenco e quindi fare clic su **OK**.

2.  Specificare una descrizione per il criterio del sito (facoltativo).

3.  Nel criterio sito o utente selezionare **Abilita comunicazioni con gli utenti federati**.

4.  Selezionare **Abilita comunicazioni con utenti federati XMPP**.

5.  Fare clic su **conferma** per salvare le modifiche apportate ai criteri per il sito o per gli utenti.

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners"></a>Per modificare un criterio esistente per i partner federati XMPP

1.  Per modificare un criterio esistente, selezionare il criterio appropriato nell'elenco, fare clic su **modifica**e quindi su **Mostra dettagli**.

2.  Modificare o aggiornare la descrizione per il criterio (facoltativo).

3.  Selezionare o deselezionare **Abilita comunicazioni con gli utenti federati**.

4.  Selezionare o deselezionare **Abilita comunicazioni con utenti federati XMPP**.

5.  Fare clic su **conferma** per salvare le modifiche apportate al criterio.

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a>Per modificare un criterio esistente per i partner federati XMPP tramite Windows PowerShell

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Digitare quanto segue in Lync Server Management Shell:
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    Un comando di esempio che imposterà il criterio globale per l'accesso degli utenti federati a true (Enabled) e l'accesso al dominio XMPP a true (Enabled):
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners-using-windows-powershell"></a>Per creare un sito o un criterio utente per partner federati XMPP con Windows PowerShell

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Digitare quanto segue in Lync Server Management Shell:
    
        New-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    Un comando di esempio che imposterà i criteri del sito per il sito Redmond per l'accesso degli utenti federati all'accesso al dominio abilitato e XMPP a Enabled:
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-delete-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a>Per eliminare un criterio esistente per i partner federati XMPP tramite Windows PowerShell

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Digitare quanto segue in Lync Server Management Shell:
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>
    
    Un comando di esempio che eliminerà un criterio utente:
    
        Remove-CsExternalAccessPolicy -Identity EAPUserPolicySetXMPP

4.  Comando di esempio che reimposta il criterio globale sui valori predefiniti:
    
        Remove-CsExternalAccessPolicy -Identity global

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Assegnare criteri di accesso per gli utenti esterni a un utente abilitato per Lync in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  
[Abilitare o disabilitare la federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  


[Gestire i partner federati XMPP per l'organizzazione in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
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

