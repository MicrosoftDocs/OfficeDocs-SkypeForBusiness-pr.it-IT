---
title: "Lync Server 2013: configurare criteri per controllare l'accesso utente federato XMPP"
description: "Lync Server 2013: configurare i criteri per controllare l'accesso utente federato XMPP."
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
ms.openlocfilehash: cdb2b7a3da6c00aa7725ecbb69856756f229ed97
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542782"
---
# <a name="configure-policies-to-control-xmpp-federated-user-access-in-lync-server-2013"></a>Configurare criteri per controllare l'accesso utente federato XMPP in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Si tratta di una documentazione preliminare e soggetta a modifiche. Gli argomenti vuoti sono inclusi come segnaposto.

Quando si configurano i criteri per il supporto di partner federati XMPP (Extensible Messaging and Presence Protocol), i criteri si applicano agli utenti dei domini federati XMPP, ma non agli utenti dei provider di servizi di messaggistica istantanea SIP (Session Initiation Protocol), ad esempio Windows Live, o ai domini federati SIP. È necessario configurare un **Partner federato XMPP** per ogni dominio federato XMPP in cui si desidera che gli utenti possano aggiungere contatti o comunicare. I criteri dei partner federati XMPP sono disponibili solo in un unico ambito; sebbene non siano definiti come criteri globali, si comportano come tali. Per definire criteri globali, sito o utente per Partner federati XMPP, è necessario configurare l'ambito dei criteri creando e configurando innanzitutto Criteri di accesso esterno per l'ambito richiesto. Per informazioni dettagliate sui tipi di criteri che è possibile configurare per l'accesso esterno e la Federazione, vedere [Managing Federation and External Access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) nella documentazione relativa alle operazioni.

<div>


> [!NOTE]  
> Tutti i criteri <STRONG>Federazione e accesso esterno</STRONG> vengono applicati mediante il provisioning di tipo in-band. I criteri applicabili all'utente, appartenenti a un sito o con ambito globale vengono comunicati al client durante l'accesso. È possibile configurare criteri per il controllo dell'accesso dei partner federati XMPP anche se non è stata abilitata la federazione XMPP per l'organizzazione. I criteri configurati, tuttavia, hanno effetto solo dopo avere distribuito, abilitato e configurato la federazione di partner XMPP per l'organizzazione. Per informazioni dettagliate sulla distribuzione e la configurazione della Federazione dei partner XMPP, vedere <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Configuring SIP Federation, XMPP Federation and Public Instant Messaging in Lync Server 2013</A> nella documentazione relativa alla distribuzione. Inoltre, se si specifica un criterio utente nel criterio di accesso esterno per controllare i partner federati XMPP, il criterio si applica solo agli utenti abilitati per Lync Server 2013 e configurati per l'utilizzo del criterio.



</div>

<div>

## <a name="to-edit-a-global-policy-for-xmpp-federated-partners"></a>Per modificare un criterio globale per i partner federati XMPP

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Accesso utente esterno** e quindi su **Criteri di accesso esterno**.

4.  Nella pagina **Criteri di accesso esterno** eseguire le operazioni seguenti per il criterio globale:

5.  Fare clic sul criterio globale, fare clic su **Modifica**, quindi su Mostra dettagli.

6.  Inserire una descrizione per il criterio globale (facoltativo).

7.  Selezionare **Abilita comunicazioni con utenti federati**.

8.  Selezionare **Abilita comunicazioni con gli utenti federati XMPP**.

9.  Fare clic su **Commit** per salvare le modifiche al criterio globale.

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners"></a>Per creare criteri sito o utente per i partner federati XMPP

1.  Fare clic su **Nuovo** e quindi su **Criteri sito** o **Criteri utente**. In **Seleziona un sito** fare clic sul sito appropriato nell'elenco e quindi fare clic su **OK**.

2.  Inserire una descrizione per il criterio del sito (facoltativo).

3.  Nel criterio sito o utente selezionare **Abilita comunicazioni con utenti federati**.

4.  Selezionare **Abilita comunicazioni con gli utenti federati XMPP**.

5.  Fare clic su **Commit** per salvare le modifiche ai criteri sito o utente.

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners"></a>Per modificare un criterio esistente per i partner federati XMPP

1.  Per modificare un criterio esistente, selezionare il criterio appropriato nell'elenco, fare clic su **Modifica** e quindi su **Mostra dettagli**.

2.  Modificare o aggiornare la descrizione del criterio (facoltativo).

3.  Selezionare o deselezionare **Abilita comunicazioni con utenti federati**.

4.  Selezionare o deselezionare **Abilita comunicazioni con gli utenti federati XMPP**.

5.  Fare clic su **Commit** per salvare le modifiche ai criteri.

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a>Per modificare un criterio esistente per i partner federati XMPP tramite Windows PowerShell

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Digitare quanto segue in Lync Server Management Shell:
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    Un comando di esempio che consentirà di impostare i criteri globali per l'accesso degli utenti federati a true (Enabled) e l'accesso al dominio XMPP a true (attivato):
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners-using-windows-powershell"></a>Per creare criteri di sito o utente per i partner federati XMPP tramite Windows PowerShell

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Digitare quanto segue in Lync Server Management Shell:
    
        New-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    Comando di esempio che abilita un criterio per il sito di Redmond per l'accesso utente federato e l'accesso ai domini XMPP:
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-delete-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a>Per eliminare un criterio esistente per i partner federati XMPP tramite Windows PowerShell

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Digitare quanto segue in Lync Server Management Shell:
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>
    
    Comando di esempio per l'eliminazione di un criterio utente:
    
        Remove-CsExternalAccessPolicy -Identity EAPUserPolicySetXMPP

4.  Comando di esempio per il ripristino dei valori predefiniti del criterio globale:
    
        Remove-CsExternalAccessPolicy -Identity global

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Assegnare un criterio di accesso utente esterno a un utente abilitato per Lync in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  
[Abilitare o disabilitare la Federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  


[Gestire i partner federati XMPP in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
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

