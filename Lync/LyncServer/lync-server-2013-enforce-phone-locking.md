---
title: 'Lync Server 2013: applicare il blocco del telefono'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enforce phone locking
ms:assetid: 1f89298b-aea9-4952-93ca-0270b565792b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520963(v=OCS.15)
ms:contentKeyID: 48183594
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c781c09db1834d85a1df4532d1484e43d74ca48
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735476"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enforce-phone-locking-in-lync-server-2013"></a>Applicare il blocco telefonico in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

I dispositivi Lync Phone Edition possono essere bloccati per motivi di sicurezza. Se si applica il blocco telefonico, il dispositivo che utilizza Lync Phone Edition si blocca dopo un periodo di tempo configurato. Quando un telefono è bloccato, un utente può effettuare chiamate ma non può accedere alle informazioni su calendario e contatti, alla segreteria telefonica o ai registri delle chiamate o utilizzare la ricerca. Per sbloccare il telefono, l'utente immette un PIN.

Per applicare il blocco telefonico, abilitarlo e configurarlo usando il pannello di controllo di Lync Server o i cmdlet di PowerShell di Lync Server. È possibile applicare il blocco telefonico a livello globale o solo all'interno del sito per cui è configurato.

<div>

## <a name="to-configure-and-enforce-the-phone-lock"></a>Per configurare e applicare il blocco telefono

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Fare clic su **client**e quindi su **Configurazione dispositivo**.

4.  Nell'elenco delle configurazioni dei dispositivi della scheda **Configurazione dispositivo** fare doppio clic sulla configurazione per la quale si desidera modificare le impostazioni di blocco del telefono.

5.  Nella finestra di dialogo **modifica configurazione dispositivo** verificare che la casella di controllo **applica blocco dispositivo** sia selezionata.

6.  In **lunghezza minima PIN**accettare il valore predefinito per il numero minimo di cifre che il pin di sblocco deve contenere o specificare un nuovo valore. L'intervallo per la lunghezza del PIN è da 4 a 15 cifre e il valore predefinito è sei.

7.  In **timeout blocco telefono**accettare il valore predefinito per il periodo di tempo minimo prima che il telefono si blocchi o specifichi un nuovo valore. L'intervallo per il timeout è compreso tra 0 e 60 minuti e il valore predefinito è 10. Immettere il valore nel formato HH: MM: SS.

8.  Fare clic su **Commit**.

</div>

<div>

## <a name="enforcing-phone-locking-by-using-windows-powershell-cmdlets"></a>Applicazione del blocco del telefono tramite i cmdlet di Windows PowerShell

Il blocco telefono può essere applicato tramite il cmdlet Set-CsUCPhoneConfiguration. Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-enable-phone-locking"></a>Per abilitare il blocco del telefono

  - Il comando seguente consente di bloccare il telefono per il sito Redmond. Per disabilitare il blocco del telefono, imposta la proprietà EnforcePhoneLock su false ($False).
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-enable-phone-locking-and-modify-the-phone-lock-timeout"></a>Per abilitare il blocco del telefono e modificare il timeout di blocco del telefono

  - Questo comando consente di bloccare il telefono e imposta anche il timeout di blocco del telefono su 30 minuti.
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True -PhoneLockTimeout "00:30:00"

</div>

<div>

## <a name="to-enable-phone-locking-throughout-the-organization"></a>Per abilitare il blocco telefonico nell'intera organizzazione

  - In questo esempio, il blocco telefonico è abilitato in tutte le impostazioni di configurazione del telefono UC in uso nell'organizzazione.
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration  -EnforcePhoneLock $True

</div>

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) .

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Gestione dell'autenticazione di Lync Server 2013](lync-server-2013-managing-lync-server-authentication.md)  


[Gestione di dispositivi, telefoni e applicazioni client in Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

