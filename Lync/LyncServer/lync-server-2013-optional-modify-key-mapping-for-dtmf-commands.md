---
title: 'Lync Server 2013: (facoltativo) modificare il mapping dei tasti per i comandi DTMF'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Modify key mapping for DTMF commands
ms:assetid: d753b78d-400c-4df2-957f-e7576b2019c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398943(v=OCS.15)
ms:contentKeyID: 48185563
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd1a6d9d2cf2e97f7b04209d1ca8aab7bdc23456
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051128"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-modify-key-mapping-for-dtmf-commands-in-lync-server-2013"></a>Optional Modificare il mapping dei tasti per i comandi DTMF in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-30_

Gli utenti delle conferenze telefoniche con accesso esterno possono premere i tasti sul tastierino del telefono per eseguire i comandi DTMF (Dual-Tone Multi-Frequency). I comandi DTMF consentono agli utenti che accedono a una conferenza di controllare le impostazioni di conferenza, ad esempio il muting e la riattivazione o il blocco e lo sblocco della conferenza, tramite la tastiera del telefono. È possibile utilizzare i cmdlet per modificare le chiavi utilizzate per i comandi DTMF. Questo passaggio è facoltativo.

<div>


> [!NOTE]  
> Per informazioni dettagliate su questi cmdlet e sulle possibili opzioni DTMF, vedere Lync Server Management Shell Documentation o la guida della riga di comando di Lync Server Management Shell.



</div>

<div>

## <a name="to-modify-the-key-mapping-of-dtmf-commands"></a>Per modificare il mapping dei tasti per i comandi DTMF

1.  Accedere al computer come membro del gruppo **RTCUniversalServerAdmins** o come membro del ruolo **Cs-ServerAdministrator** o **CsAdministrator** .

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Eseguire il comando seguente al prompt:
    
        Get-CsDialinConferencingDtmfConfiguration
    
    Questo cmdlet restituisce le impostazioni DTMF utilizzate per le conferenze telefoniche con accesso esterno.

4.  Eseguire il cmdlet seguente e specificare il tasto da premere per ogni opzione che si desidera modificare:
    
        Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
        [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
        [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
        [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
        [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
    
    Questo cmdlet consente di modificare le impostazioni DTMF utilizzate per le conferenze telefoniche con accesso esterno.
    
    Ad esempio:
    
        Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
    
    In questo esempio viene scambiato il tasto premuto per abilitare o disabilitare gli annunci e il tasto premuto per disattivare e riattivare l'audio di tutti i partecipanti. Poiché non viene specificata alcuna identità, queste modifiche sono valide per le impostazioni DTMF globali.

5.  Optional Per creare ulteriori insiemi di comandi DTMF per siti specifici, utilizzare il cmdlet **New-CsDialInConferencingDtmfConfiguration** con un'identità del sito. Quando si creano nuove impostazioni DTMF per i siti, le impostazioni del sito hanno la precedenza sulle impostazioni globali. Per informazioni dettagliate, vedere la documentazione di Lync Server Management Shell o la guida della riga di comando di Lync Server Management Shell.

</div>

</div>

<span> </span>

</div>

</div>

</div>

