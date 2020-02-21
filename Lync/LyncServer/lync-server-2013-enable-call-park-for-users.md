---
title: 'Lync Server 2013: abilitare il parcheggio di chiamata per gli utenti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Call Park for users
ms:assetid: 9430763f-3394-467c-9c6d-426bf761604e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398753(v=OCS.15)
ms:contentKeyID: 48184814
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3046cc7daf0dd1fbaba16ffff4e8f41ee6d2e757
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-call-park-for-users-in-lync-server-2013"></a>Abilitare il parcheggio di chiamata per gli utenti in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-11_

Gli utenti non possono parcheggiare le chiamate o recuperare le chiamate parcheggiate finché non sono abilitate per il parcheggio di chiamata nel criterio vocale.

<div>


> [!NOTE]  
> Per impostazione predefinita, il parcheggio di chiamata è disabilitato per tutti gli utenti.



</div>

È possibile abilitare il parcheggio di chiamata nell'ambito globale o nell'ambito del sito o nell'ambito dell'utente. L'ambito utente ha la precedenza rispetto all'ambito a livello di sito, che a sua volta ha la precedenza rispetto all'ambito globale. Se si dispone di più criteri vocali, esaminare tutti i criteri per abilitare il parcheggio di chiamata, non solo il criterio globale.

<div>

## <a name="to-use-lync-server-control-panel-to-enable-call-park-for-users"></a>Per utilizzare il pannello di controllo di Lync Server per abilitare il parcheggio di chiamata per gli utenti

1.  Accedere al computer come membro del gruppo **RTCUniversalServerAdmins** o come membro del ruolo amministrativo **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Routing vocale**.

4.  Fare clic sulla scheda **Criteri vocali**.

5.  Fare doppio clic su un criterio esistente per aprire la finestra di dialogo **Modifica criterio vocale**.

6.  In **Funzionalità di chiamata** selezionare **Abilita parcheggio di chiamata**.

7.  Fare clic su **OK** per salvare il criterio vocale.

</div>

<div>

## <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>Per utilizzare i cmdlet per abilitare il parcheggio di chiamata per gli utenti

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo amministrativo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Eseguire: 
    
        Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
    
    Ad esempio, per abilitare il parcheggio di chiamata per il criterio vocale globale predefinito:
    
        Set-CsVoicePolicy -EnableCallPark $true

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

