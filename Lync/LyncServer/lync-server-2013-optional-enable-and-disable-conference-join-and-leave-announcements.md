---
title: (Facoltativo) Abilitare e disabilitare gli annunci di partecipazione e abbandono delle conferenze
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Enable and disable conference join and leave announcements
ms:assetid: c9529568-e66c-48d8-aef2-9072f9c336ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398834(v=OCS.15)
ms:contentKeyID: 48185403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 778969dfa5ed6b84fdbcd2b204e497f8d649f1a6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979899"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-enable-and-disable-conference-join-and-leave-announcements-in-lync-server-2013"></a>(Facoltativo) Abilitare e disabilitare gli annunci di partecipazione e abbandono delle conferenze in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-30_

Quando gli utenti con accesso esterno entrano o lasciano una conferenza, l'applicazione di annunci per conferenze può annunciare l'entrata o l'uscita suonando un tono o pronunciando i loro nomi. È possibile modificare la modalità di funzionamento degli annunci eseguendo i cmdlet. Questo passaggio è facoltativo.

<div>

## <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>Per modificare il comportamento dell'annuncio per la conferenza e il permesso

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo **Cs-ServerAdministrator** o **CsAdministrator** .

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Eseguire la procedura seguente al prompt dei comandi:
    
        Get-CsDialinConferencingConfiguration
    
    Questo cmdlet recupera informazioni sul fatto che i partecipanti debbano registrare il loro nome quando partecipano a una conferenza e come risponde Lync Server quando i partecipanti partecipano o lasciano una conferenza telefonica con accesso esterno.

4.  Eseguire la procedura seguente al prompt dei comandi:
    
        Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
        [-EnableNameRecording <$true | $false>]
        [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
        [-EntryExitAnnouncementsType <UseNames | ToneOnly]
    
    **EnableNameRecording**   determina se i partecipanti anonimi vengono invitati a registrare il loro nome prima di accedere alla conferenza. Il valore predefinito è "$true", che indica che ai partecipanti anonimi viene richiesto di indicare il loro nome quando partecipano a una conferenza. I partecipanti autenticati non registrano il proprio nome perché viene usato il nome visualizzato.
    
    **EntryExitAnnouncementsEnabledByDefault**   indica se gli annunci sono attivati o disattivati per impostazione predefinita. Il valore predefinito è "$false", che indica che per impostazione predefinita non ci sono annunci quando i partecipanti partecipano o lasciano una conferenza. L'organizzatore della riunione può eseguire l'override di questa impostazione durante la pianificazione di una riunione.
    
    **EntryExitAnnouncementsType**   indica l'azione eseguita ogni volta che un partecipante partecipa o esce da una conferenza per cui sono abilitati gli annunci. Il valore predefinito è "UseNames", che indica che è presente un annuncio simile al seguente: "Ken si è unito alla conferenza" quando gli annunci sono attivati.
    
    Queste impostazioni possono essere configurate nell'ambito globale o nell'ambito del sito. Le impostazioni configurate nell'ambito del sito hanno la precedenza sulle impostazioni configurate nell'ambito globale.
    
    Ad esempio:
    
        Set-CsDialinConferencingConfiguration -Identity site:Redmond
        -EnableNameRecording $false
        -EntryExitAnnouncementsEnabledByDefault $true
        -EntryExitAnnouncementsType ToneOnly
    
    In questo esempio le impostazioni vengono configurate nell'ambito del sito per Redmond. Gli annunci sono attivati, ma ai partecipanti non viene chiesto di pronunciare il loro nome quando partecipano a una conferenza. Viene riprodotto un tono quando i partecipanti entrano o lasciano una conferenza.

</div>

</div>

<span> </span>

</div>

</div>

</div>

