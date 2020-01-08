---
title: 'Lync Server 2013: (Facoltativo) Modificare il mapping dei tasti per i comandi DTMF'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Modify key mapping for DTMF commands
ms:assetid: d753b78d-400c-4df2-957f-e7576b2019c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398943(v=OCS.15)
ms:contentKeyID: 48185563
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd1a9fbe17a07403fbf0195026d44b490680973e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-modify-key-mapping-for-dtmf-commands-in-lync-server-2013"></a>(Facoltativo) Modificare il mapping dei tasti per i comandi DTMF in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-30_

Gli utenti dei servizi di conferenza telefonica con accesso esterno possono premere i tasti sul tastierino telefonico per eseguire i comandi DTMF (Dual-Tone Multi-Frequency). I comandi DTMF consentono agli utenti che effettuano la chiamata a una conferenza di controllare le impostazioni della conferenza, ad esempio disattivare e riattivare il segnale, o bloccare o sbloccare la conferenza, usando la tastiera del telefono. Puoi usare i cmdlet per modificare le chiavi usate per i comandi DTMF. Questo passaggio è facoltativo.

<div>


> [!NOTE]  
> Per informazioni dettagliate su questi cmdlet e sulle possibili opzioni DTMF, vedere documentazione di Lync Server Management Shell o guida della riga di comando di Lync Server Management Shell.



</div>

<div>

## <a name="to-modify-the-key-mapping-of-dtmf-commands"></a>Per modificare il mapping delle chiavi dei comandi DTMF

1.  Accedere al computer come membro del gruppo **RTCUniversalServerAdmins** oppure come membro del ruolo **Cs-ServerAdministrator** o **CsAdministrator** .

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Eseguire la procedura seguente al prompt dei comandi:
    
        Get-CsDialinConferencingDtmfConfiguration
    
    Questo cmdlet restituisce le impostazioni DTMF usate per i servizi di conferenza telefonica con accesso esterno.

4.  Eseguire il cmdlet seguente e specificare la chiave da premere per ogni opzione che si vuole modificare:
    
        Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
        [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
        [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
        [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
        [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
    
    Questo cmdlet modifica le impostazioni DTMF usate per i servizi di conferenza telefonica con accesso esterno.
    
    Ad esempio:
    
        Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
    
    Questo esempio scambia il tasto premuto per abilitare o disabilitare gli annunci e la chiave che viene premuta per disattivare e riattivare l'audio di tutti i partecipanti. Poiché non è specificata alcuna identità, le modifiche apportate alle impostazioni DTMF globali sono valide.

5.  Opzionale Per creare altri set di comandi DTMF per siti specifici, usare il cmdlet **New-CsDialInConferencingDtmfConfiguration** con un'identità del sito. Quando si creano nuove impostazioni DTMF per i siti, le impostazioni del sito hanno la precedenza sulle impostazioni globali. Per informazioni dettagliate, vedere documentazione di Lync Server Management Shell o guida della riga di comando di Lync Server Management Shell.

</div>

</div>

<span> </span>

</div>

</div>

</div>

