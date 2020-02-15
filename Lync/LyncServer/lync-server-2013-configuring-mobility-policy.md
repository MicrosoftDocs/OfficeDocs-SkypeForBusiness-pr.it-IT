---
title: 'Lync Server 2013: configurazione di criteri per dispositivi mobili'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring mobility policy
ms:assetid: 595536e0-9bb3-49a3-8d13-1a77351ebc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690018(v=OCS.15)
ms:contentKeyID: 48184204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6410e50a5e7d84de152b9a4e4bd1f962c5a3c9bd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008408"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-policy-in-lync-server-2013"></a>Configurazione di criteri per dispositivi mobili in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-13_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 fornisce i criteri per dispositivi mobili che determinano gli utenti che possono utilizzare le funzionalità per dispositivi mobili, la chiamata tramite lavoro, il VoIP (Voice over IP) o il video e se la connessione WiFi sarà necessaria per VoIP o video. La funzionalità di chiamata tramite lavoro consente a un utente di telefonia mobile di effettuare e ricevere chiamate su un telefono cellulare utilizzando un numero di telefono di lavoro invece del numero di cellulare. Questa funzionalità impedisce alla parte chiamata di visualizzare il numero di telefono cellulare del chiamante e di evitare che i costi di chiamata in uscita vengano configurati da un utente. La configurazione di VoIP e video rende possibile agli utenti di ricevere e fare chiamate VoIP e video. Le impostazioni per l'utilizzo di Wi-Fi definiscono se il dispositivo di un utente dovrà utilizzare una rete WiFi su una rete di dati cellulare.

Per impostazione predefinita, la mobilità, la chiamata tramite lavoro e le funzionalità VoIP e video sono abilitate. Le impostazioni per richiedere il WiFi per VoIp e video sono disattivate. Gli amministratori possono stabilire chi ha accesso a tali funzionalità eseguendo un cmdlet. È possibile disattivare le opzioni globalmente, a livello di sito o a livello di singoli utenti.

Per poter utilizzare le funzionalità di mobilità e Chiama da ufficio, gli utenti devono soddisfare i prerequisiti seguenti:

  - Gli utenti devono essere abilitati per Lync Server 2013.

  - Gli utenti devono essere abilitati per VoIP aziendale.

  - Agli utenti devono essere assegnati criteri di mobilità con l'opzione **EnableMobility** impostata su True.

Affinché gli utenti siano in grado di utilizzare Chiama da ufficio, è necessario che soddisfino i due prerequisiti aggiuntivi seguenti:

  - Agli utenti devono essere assegnati criteri vocali con l'opzione **Abilita squillo simultaneo dei telefoni** selezionata.

  - Agli utenti devono essere assegnati criteri di mobilità con l'opzione **EnableOutsideVoice** impostata su True.

<div>


> [!NOTE]  
> Gli utenti che non sono abilitati per VoIP aziendale possono utilizzare i propri dispositivi mobili per consentire a Lync di chiamare Lync Voice over IP, oppure possono partecipare a conferenze usando il collegamento fare clic per partecipare ai propri dispositivi mobili, se si assegnano a tali utenti le opzioni appropriate per i criteri vocali. Per informazioni dettagliate, vedere <A href="lync-server-2013-defining-your-mobility-requirements.md">definizione dei requisiti per dispositivi mobili per Lync Server 2013</A>.



</div>

Per informazioni dettagliate sull'abilitazione degli utenti per Lync Server 2013, vedere [disabilitare o riabilitare l'account utente per Lync server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md). Per informazioni dettagliate sull'abilitazione degli utenti per VoIP aziendale, vedere [abilitare gli utenti per VoIP aziendale in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md). Per informazioni dettagliate sull'impostazione delle opzioni per i criteri vocali, vedere [Modify a Voice Policy e Configure PSTN Usage Records in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).

<div>

## <a name="to-modify-global-mobility-policy"></a>Per modificare i criteri di mobilità globali

1.  Accedere a qualsiasi computer in cui sono installati Lync Server Management Shell e OCSCore come membri del ruolo CsAdministrator.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Disattivare globalmente l'accesso alle funzionalità di mobilità e Chiama da ufficio. Nella riga di comando digitare:
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    
    <div>
    

    > [!NOTE]  
    > È possibile disattivare Chiama da ufficio senza disattivare l'accesso alla funzionalità di mobilità. Non è tuttavia possibile disattivare le funzionalità di mobilità senza disattivare anche Chiama da ufficio.

    
    </div>

</div>

<div>

## <a name="to-modify-mobility-policy-by-site"></a>Per modificare i criteri di mobilità a livello di sito

1.  Accedere a qualsiasi computer in cui sono installati Lync Server Management Shell e OCSCore come membri del ruolo CsAdministrator.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Creare criteri a livello di sito e disattivare VoIP e video e abilitare Richiedi WiFi per l'audio IP e per il video IP per sito. Nella riga di comando digitare il comando seguente:
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

</div>

<div>

## <a name="to-modify-mobility-policy-by-user"></a>Per modificare i criteri di mobilità a livello di utente

1.  Accedere a qualsiasi computer in cui sono installati Lync Server Management Shell e OCSCore come membri del ruolo CsAdministrator.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Creare nuovi criteri di mobilità a livello di utente e disattivare le funzionalità di mobilità e Chiama da ufficio per un utente specifico. Nella riga di comando digitare:
    
        New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
    
    È possibile disattivare Chiama da ufficio senza disattivare l'accesso alla funzionalità di mobilità. Non è tuttavia possibile disattivare le funzionalità di mobilità senza disattivare anche Chiama da ufficio.
    
    Ad esempio:
    
        New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity -MobileUser1@contoso.com -PolicyName Tag:disableOutsideVoice

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Disabilitare o riabilitare l'account utente per Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[Abilitare gli utenti per VoIP aziendale in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)  
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

