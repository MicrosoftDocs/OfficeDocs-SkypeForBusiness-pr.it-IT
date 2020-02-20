---
title: Optional Abilitare e disabilitare gli annunci di partecipazione alla conferenza e di uscita
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Enable and disable conference join and leave announcements
ms:assetid: c9529568-e66c-48d8-aef2-9072f9c336ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398834(v=OCS.15)
ms:contentKeyID: 48185403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 67939f67e90e6c0cc044ea871560647cae9e4021
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153426"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-enable-and-disable-conference-join-and-leave-announcements-in-lync-server-2013"></a>Optional Abilitare e disabilitare gli annunci di partecipazione alla conferenza e di uscita in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-30_

Quando gli utenti con accesso esterno si uniscono o lasciano una conferenza, l'applicazione annuncio per le conferenze può annunciare la propria entrata o uscita suonando un tono o pronunciando i propri nomi. Il funzionamento degli annunci può essere modificato eseguendo i cmdlet. Questo passaggio è facoltativo.

<div>

## <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>Per modificare il comportamento di partecipazione a una conferenza o di abbandono della stessa

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo **Cs-ServerAdministrator** o **CsAdministrator**.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Eseguire il comando seguente al prompt:
    
        Get-CsDialinConferencingConfiguration
    
    Questo cmdlet recupera le informazioni sul fatto che i partecipanti devono registrare il proprio nome quando partecipano a una conferenza e in che modo Lync Server risponde quando i partecipanti si uniscono o lasciano una conferenza telefonica con accesso esterno.

4.  Eseguire il comando seguente al prompt:
    
        Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
        [-EnableNameRecording <$true | $false>]
        [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
        [-EntryExitAnnouncementsType <UseNames | ToneOnly]
    
    **EnableNameRecording**   determina se ai partecipanti anonimi viene richiesto di registrare il proprio nome prima di accedere alla conferenza. Il valore predefinito è "$true" e indica che ai partecipanti anonimi viene richiesto di specificare il proprio nome durante l'accesso a una conferenza. I partecipanti autenticati non registrano il proprio nome perché viene utilizzato il nome visualizzato.
    
    **EntryExitAnnouncementsEnabledByDefault**   indica se gli annunci sono attivati o disattivati per impostazione predefinita. Il valore predefinito è "$false" e indica che per impostazione predefinita non vengono visualizzati annunci quando gli utenti partecipano a una conferenza o la abbandonano. L'organizzatore della riunione può sostituire questa impostazione durante la pianificazione della riunione.
    
    **EntryExitAnnouncementsType**   indica l'azione intrapresa ogni volta che un partecipante si unisce o lascia una conferenza per la quale gli annunci sono abilitati. Il valore predefinito è "UseNames" e indica la visualizzazione di un annuncio simile al seguente: "Davide Garghentini si è unito alla conferenza" quando gli annunci sono attivati.
    
    È possibile configurare queste impostazioni a livello globale o di sito. Le impostazioni configurate a livello di sito hanno la precedenza su quelle configurate a livello globale.
    
    Ad esempio:
    
        Set-CsDialinConferencingConfiguration -Identity site:Redmond
        -EnableNameRecording $false
        -EntryExitAnnouncementsEnabledByDefault $true
        -EntryExitAnnouncementsType ToneOnly
    
    In questo esempio le impostazioni vengono configurate al livello del sito di Redmond. Gli annunci sono attivati ma ai partecipanti non viene richiesto di specificare il proprio nome durante l'accesso a una conferenza. Quando i partecipanti accedono a una conferenza o la abbandonano viene riprodotto un segnale acustico.

</div>

</div>

<span> </span>

</div>

</div>

</div>

