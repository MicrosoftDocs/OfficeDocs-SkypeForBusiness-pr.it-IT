---
title: 'Lync Server 2013: configurazione della modalità privacy della presenza avanzata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring enhanced presence privacy mode
ms:assetid: e7a6b873-486d-4dfb-a967-c48f61f237f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399028(v=OCS.15)
ms:contentKeyID: 48185664
ms.date: 12/09/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c16e33197ed28744df126d672385359f5eb8781b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042988"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enhanced-presence-privacy-mode-in-lync-server-2013"></a>Configurazione della modalità privacy della presenza avanzata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-12-08_

Con la modalità di privacy della presenza avanzata, gli utenti possono limitare le informazioni sulla presenza in modo che siano visibili solo ai contatti elencati nell'elenco contatti di Lync 2013. I cmdlet **New-CsPrivacyConfiguration** e **Set-CsPrivacyConfiguration** dispongono di un parametro EnablePrivacyMode che controlla questa opzione. Quando EnablePrivacyMode è impostato su true, l'opzione per limitare le informazioni sulla presenza ai contatti diventa disponibile nelle opzioni di stato di Lync 2013. Se invece EnablePrivacyMode è impostato su False, gli utenti possono scegliere di consentire sempre a tutti di visualizzare le informazioni sulla presenza oppure di accettare qualsiasi modifica futura apportata dall'amministratore alla modalità privacy.

<div>


> [!IMPORTANT]  
> Le impostazioni relative alla privacy di Lync 2013 e Lync 2010 non sono rispettate dalle versioni precedenti (Microsoft Office Communicator 2007 R2 o Microsoft Office Communicator 2007). Se le versioni precedenti di Office Communicator sono consentite per l'accesso, lo stato di un utente di Lync 2013, le informazioni di contatto o l'immagine potrebbero essere visualizzate da una persona che non è stata autorizzata a visualizzarla. Inoltre, le impostazioni relative alla privacy di un utente di Lync 2013 vengono reimpostate se successivamente accede con la versione precedente di Communicator.<BR>Per questi motivi, in uno scenario di migrazione, prima di abilitare la modalità privacy della presenza avanzata, eseguire le operazioni seguenti: 
> <UL>
> <LI>
> <P>Verificare che tutti gli utenti dispongano di Lync 2013 installato.</P>
> <LI>
> <P>Definire una regola dei criteri di versione dei client per impedire alle precedenti versioni di Communicator di accedere.</P></LI></UL>



</div>

<div>

## <a name="to-enable-enhanced-presence-privacy-mode"></a>Per abilitare la modalità privacy della presenza avanzata

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Eseguire il comando seguente:
    
        Get-CsPrivacyConfiguration | Set-CsPrivacyConfiguration -EnablePrivacyMode $True
    
    Questo comando abilita la modalità privacy per tutte le impostazioni di configurazione della privacy attualmente in uso nell'organizzazione. Per ulteriori informazioni sul modo in cui la configurazione dei criteri per la modalità privacy della presenza di Lync Server è in grado di gestire la presenza del contatto per il client Lync 2013, vedere l'articolo Microsoft KB che [Abilita Lync Server Enhanced Presence privacy mode aggiorna lo stato di presenza di alcuni contatti di Lync su "non disponibile"](http://support.microsoft.com/kb/3020057).

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

