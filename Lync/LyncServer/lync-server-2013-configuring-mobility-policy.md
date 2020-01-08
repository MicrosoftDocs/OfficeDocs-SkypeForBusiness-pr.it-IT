---
title: 'Lync Server 2013: Configurazione dei criteri per dispositivi mobili'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring mobility policy
ms:assetid: 595536e0-9bb3-49a3-8d13-1a77351ebc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690018(v=OCS.15)
ms:contentKeyID: 48184204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7f71252064cef521058aba17a3c220a948e23c7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-policy-in-lync-server-2013"></a>Configurazione dei criteri per dispositivi mobili in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-13_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 offre criteri per la mobilità che determinano chi può usare le caratteristiche di mobilità, chiama tramite lavoro, Voice over IP (VoIP) o video e se il WiFi sarà necessario per il VoIP o il video. La caratteristica chiamata tramite lavoro consente a un utente mobile di effettuare e ricevere chiamate su un telefono cellulare usando un numero di telefono dell'ufficio invece del numero di cellulare. Questa caratteristica impedisce alla persona chiamata di visualizzare il numero di cellulare del chiamante e consente a un utente di evitare oneri per le chiamate in uscita. La configurazione di VoIP e video consente agli utenti di ricevere e effettuare chiamate VoIP e video. Le impostazioni per l'utilizzo di WiFi definiscono se il dispositivo di un utente deve usare una rete WiFi tramite una rete dati cellulare.

Per impostazione predefinita, la mobilità, la chiamata tramite lavoro e le funzionalità VoIP e video sono abilitate. Le impostazioni per richiedere il WiFi per VoIp e video sono disabilitate. Gli amministratori possono determinare chi ha accesso a queste funzionalità eseguendo un cmdlet. È possibile disattivare le opzioni a livello globale, per sito o per utente.

Per poter usare le caratteristiche di mobilità e la chiamata tramite lavoro, gli utenti devono soddisfare i prerequisiti seguenti:

  - Gli utenti devono essere abilitati per Lync Server 2013.

  - Gli utenti devono essere abilitati per VoIP aziendale.

  - Agli utenti deve essere assegnato un criterio di mobilità con l'opzione **EnableMobility** impostata su true.

Affinché gli utenti possano usare la chiamata tramite il lavoro, devono soddisfare i due prerequisiti aggiuntivi seguenti:

  - Agli utenti deve essere assegnato un criterio vocale con l'opzione **Abilita squillo simultaneo dei telefoni** selezionata.

  - Agli utenti deve essere assegnato un criterio di mobilità con l'opzione **EnableOutsideVoice** impostata su true.

<div>


> [!NOTE]  
> Gli utenti che non sono abilitati per Enterprise Voice possono usare i loro dispositivi mobili per consentire a Lync di eseguire chiamate VoIP (Voice over IP) di Lync o possono partecipare a conferenze usando il collegamento fare clic per partecipare ai loro dispositivi mobili, se si assegnano gli utenti le opzioni appropriate per il criterio vocale. Per informazioni dettagliate, vedere <A href="lync-server-2013-defining-your-mobility-requirements.md">definizione dei requisiti di mobilità per Lync Server 2013</A>.



</div>

Per informazioni dettagliate sull'abilitazione degli utenti per Lync Server 2013, vedere [disabilitare o riattivare l'account utente per Lync server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md). Per informazioni dettagliate sull'abilitazione degli utenti per VoIP aziendale, vedere [abilitare gli utenti per VoIP aziendale in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md). Per informazioni dettagliate sull'impostazione delle opzioni dei criteri vocali, vedere [modificare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).

<div>

## <a name="to-modify-global-mobility-policy"></a>Per modificare i criteri di mobilità globale

1.  Accedere a qualsiasi computer in cui sono installati Lync Server Management Shell e OCSCore come membro del ruolo CsAdministrator.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Disattivare l'accesso alla mobilità e chiamare tramite lavoro a livello globale. Nella riga di comando digitare:
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    
    <div>
    

    > [!NOTE]  
    > È possibile disattivare la chiamata tramite lavoro senza disattivare l'accesso alla mobilità. Tuttavia, non è possibile disattivare la mobilità senza disattivare la chiamata anche tramite lavoro.

    
    </div>

</div>

<div>

## <a name="to-modify-mobility-policy-by-site"></a>Per modificare i criteri di mobilità per sito

1.  Accedere a qualsiasi computer in cui sono installati Lync Server Management Shell e OCSCore come membro del ruolo CsAdministrator.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Creare un criterio a livello di sito e disattivare VoIP e video e abilitare Richiedi WiFi per l'audio IP e per il video IP per sito. Nella riga di comando digitare:
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

</div>

<div>

## <a name="to-modify-mobility-policy-by-user"></a>Per modificare i criteri di mobilità per utente

1.  Accedere a qualsiasi computer in cui sono installati Lync Server Management Shell e OCSCore come membro del ruolo CsAdministrator.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Creare criteri di mobilità a livello di utente e disattivare la mobilità e la chiamata tramite il lavoro da parte dell'utente. Nella riga di comando digitare:
    
        New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
    
    È possibile disattivare la chiamata tramite lavoro senza disattivare l'accesso alla mobilità. Tuttavia, non è possibile disattivare la mobilità senza disattivare la chiamata anche tramite lavoro.
    
    Ad esempio:
    
        New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity -MobileUser1@contoso.com -PolicyName Tag:disableOutsideVoice

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Disabilitare o riattivare l'account utente per Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[Consentire agli utenti di VoIP aziendale in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)  
[Modificare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  


[Definizione dei requisiti per dispositivi mobili per Lync Server 2013](lync-server-2013-defining-your-mobility-requirements.md)  


[New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)  
[Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)  
[Get-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)  
[Grant-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy)  
[Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

