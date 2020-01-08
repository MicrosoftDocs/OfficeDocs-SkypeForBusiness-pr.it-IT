---
title: 'Lync Server 2013: configurazione della modalità di privacy avanzata della presenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring enhanced presence privacy mode
ms:assetid: e7a6b873-486d-4dfb-a967-c48f61f237f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399028(v=OCS.15)
ms:contentKeyID: 48185664
ms.date: 12/09/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 878691cd7b39d893b416a128f937d2aad1e561b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978780"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enhanced-presence-privacy-mode-in-lync-server-2013"></a>Configurazione della modalità di privacy della presenza avanzata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-12-08_

Con la modalità di privacy della presenza avanzata, gli utenti possono limitare le informazioni sulla presenza in modo che siano visibili solo ai contatti elencati nell'elenco contatti di Lync 2013. I cmdlet **New-CsPrivacyConfiguration** e **Set-CsPrivacyConfiguration** hanno un parametro EnablePrivacyMode che controlla questa opzione. Quando EnablePrivacyMode è impostato su true, l'opzione per limitare le informazioni sulla presenza ai contatti diventa disponibile nelle opzioni di stato di Lync 2013. Quando EnablePrivacyMode è impostato su false, gli utenti possono scegliere di consentire sempre a tutti di visualizzare le informazioni sulla presenza o di rispettare le eventuali modifiche future che l'amministratore apporta alla modalità privacy.

<div>


> [!IMPORTANT]  
> Le impostazioni di privacy di Lync 2013 e Lync 2010 non vengono rispettate dalle versioni precedenti (Microsoft Office Communicator 2007 R2 o Microsoft Office Communicator 2007). Se è consentito l'accesso alle versioni precedenti di Office Communicator, lo stato di un utente di Lync 2013, le informazioni di contatto o l'immagine potrebbero essere visualizzati da una persona che non è stata autorizzata a visualizzarla. Inoltre, le impostazioni di privacy di un utente di Lync 2013 vengono reimpostate se successivamente accede con la versione precedente di Communicator.<BR>Per questi motivi, in uno scenario di migrazione, prima di abilitare la modalità di privacy avanzata della presenza: 
> <UL>
> <LI>
> <P>Assicurarsi che tutti gli utenti dispongano di Lync 2013 installati.</P>
> <LI>
> <P>Definire una regola di criteri di versione client per impedire l'accesso alle versioni precedenti di Communicator.</P></LI></UL>



</div>

<div>

## <a name="to-enable-enhanced-presence-privacy-mode"></a>Per abilitare la modalità di privacy della presenza avanzata

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Eseguire il comando seguente:
    
        Get-CsPrivacyConfiguration | Set-CsPrivacyConfiguration -EnablePrivacyMode $True
    
    Questo comando consente di abilitare la modalità privacy per tutte le impostazioni di configurazione della privacy attualmente in uso nell'organizzazione. Per altre informazioni sul modo in cui le configurazioni dei criteri di privacy della presenza avanzata di Lync Server gestiscono la presenza dei contatti per il client Lync 2013, vedere l'articolo Microsoft Knowledge che [Abilita la modalità di privacy della presenza avanzata di Lync Server per aggiornare lo stato presenza di alcuni contatti di Lync a "non disponibile"](http://support.microsoft.com/kb/3020057).

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Get-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPrivacyConfiguration)  
[New-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsPrivacyConfiguration)  
[Set-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

