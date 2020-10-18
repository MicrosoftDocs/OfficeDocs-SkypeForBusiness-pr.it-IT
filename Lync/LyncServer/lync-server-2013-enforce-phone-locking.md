---
title: 'Lync Server 2013: applicare il blocco del telefono'
description: 'Lync Server 2013: applicare il blocco del telefono.'
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
ms.openlocfilehash: 5afae4fa27edf9378bacc39a29697c9607b25c07
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575602"
---
# <a name="enforce-phone-locking-in-lync-server-2013"></a>Applicare il blocco del telefono in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

I dispositivi Lync Phone Edition possono essere bloccati per motivi di sicurezza. Se si applica il blocco del telefono, il dispositivo che esegue Lync Phone Edition si blocca dopo un periodo di tempo configurabile. Quando un telefono è bloccato, un utente può effettuare chiamate ma non può accedere alle informazioni su calendario e contatti, alla segreteria telefonica o ai registri di chiamata oppure utilizza la funzionalità di ricerca. Per sbloccare il telefono, l'utente immette un PIN.

Per applicare il blocco del telefono, abilitarlo e configurarlo utilizzando il pannello di controllo di Lync Server o i cmdlet di PowerShell di Lync Server. È possibile applicare il blocco del telefono a livello globale o solo all'interno del sito per il quale è configurato.

<div>

## <a name="to-configure-and-enforce-the-phone-lock"></a>Per configurare e applicare il blocco del telefono

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Fare clic su **Client** e quindi su **Configurazione dispositivo**.

4.  Nell'elenco delle configurazioni dei dispositivi nella scheda **Configurazione dispositivo** fare doppio clic sulla configurazione per cui si desidera modificare le impostazioni di blocco del telefono.

5.  Nella finestra di dialogo **Modifica configurazione dispositivo** verificare che la casella di controllo **Applica blocco dispositivo** sia selezionata.

6.  Nella **lunghezza minima del pin**, accettare il valore predefinito per il numero minimo di cifre che il pin di sblocco deve contenere oppure specificare un nuovo valore. L'intervallo per la lunghezza del PIN è compreso tra quattro e 15 cifre e il valore predefinito è sei.

7.  Nel **timeout di blocco del telefono**, accettare il valore predefinito per il periodo di tempo minimo prima che il telefono si blocchi o specifichi un nuovo valore. L'intervallo per il timeout è compreso tra 0 e 60 minuti e il valore predefinito è 10. Immettere il valore nel formato HH: MM: SS.

8.  Fare clic su **Commit**.

</div>

<div>

## <a name="enforcing-phone-locking-by-using-windows-powershell-cmdlets"></a>Applicazione del blocco del telefono tramite i cmdlet di Windows PowerShell

È possibile applicare il blocco del telefono utilizzando il cmdlet Set-CsUCPhoneConfiguration. Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-enable-phone-locking"></a>Per abilitare il blocco del telefono

  - Il comando seguente attiva il blocco telefono per il sito di Redmond. Per disattivare il blocco telefono, impostare la proprietà EnforcePhoneLock su False ($False).
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-enable-phone-locking-and-modify-the-phone-lock-timeout"></a>Per abilitare il blocco del telefono e modificare il timeout di blocco del telefono

  - Questo comando attiva il blocco telefono e imposta il relativo timeout su 30 minuti.
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True -PhoneLockTimeout "00:30:00"

</div>

<div>

## <a name="to-enable-phone-locking-throughout-the-organization"></a>Per abilitare il blocco del telefono all'interno dell'organizzazione

  - In questo esempio il blocco telefono viene attivato su tutte le impostazioni di configurazione dei telefoni UC in uso nell'organizzazione.
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration  -EnforcePhoneLock $True

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) .

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

