---
title: 'Lync Server 2013: trasferire gli utenti in un altro pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move users to another pool
ms:assetid: e7b4968c-0e9d-4d56-b5f1-9edf0f7206f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182600(v=OCS.15)
ms:contentKeyID: 48185879
ms.date: 02/09/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7dffa2e7651e056d9dc14b1e261134783d0fd193
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756740"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-users-to-another-pool-in-lync-server-2013"></a>Trasferire utenti in un altro pool in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2018-02-09_

È possibile usare il pannello di controllo di Lync Server per assegnare gli utenti a un server o un pool specifico.

<div>


> [!TIP]  
> Lo spostamento di tutti gli utenti esistenti da un pool di origine che utilizza Lync Server 2010 o versioni precedenti in un pool di destinazione di Lync Server 2013 in un ambiente di Active Directory complesso può causare una replica di Active Directory più lenta. Per evitare questo problema, è possibile usare i filtri di ricerca per trasferire gli utenti da pool che esegue Lync Server 2010 o versioni precedenti separatamente oppure è possibile usare Lync Server Management Shell per trasferire gli utenti con i cmdlet. Inoltre, la funzionalità di filtro funziona con gli utenti di Lync Server 2013.



</div>

<div>

## <a name="to-move-selected-users-to-a-different-server-or-pool"></a>Per trasferire gli utenti selezionati in un altro server o pool

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **utenti**.

4.  Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, nome, cognome, nome account di Security Accounts Manager (Sam), indirizzo SIP o URI (Uniform Resource Identifier) linea dell'account utente desiderato, quindi fare clic su **trova**.

5.  Nella tabella selezionare un utente o utenti specifici nell'elenco.

6.  Nel menu **azione** fare clic su **Trasferisci utenti selezionati in pool**.

7.  In **Move users**selezionare il pool in cui si vuole trasferire gli utenti nel **pool di registrar di destinazione**.

8.  Opzionale Se il server o il pool di destinazione non è disponibile, selezionare la casella di controllo **forza** .
    
    <div>
    

    > [!Caution]  
    > Se si seleziona <STRONG>forza</STRONG>, l'account utente viene spostato, ma i dati utente associati tali conferenze e contatti pianificati non vengono spostati.

    
    </div>

</div>

<div>

## <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a>Per trasferire tutti gli utenti da un server o da un pool a un altro server o pool

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **utenti**.

4.  Nel menu **azione** fare clic su **Trasferisci tutti gli utenti in pool**.

5.  In **Move users**selezionare il pool che contiene gli account utente che si desidera trasferire nel **pool di registrazione di origine**.

6.  Nel **pool di registrar di destinazione**selezionare il pool a cui si vuole trasferire gli utenti.

7.  Opzionale Se il server o il pool di destinazione non è disponibile, selezionare la casella di controllo **forza** .
    
    <div>
    

    > [!Caution]  
    > Se si seleziona <STRONG>forza</STRONG>, l'account utente viene spostato, ma i dati utente associati tali conferenze e contatti pianificati non vengono spostati.

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a>Per trasferire gli utenti da un pool a un altro tramite un filtro

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **utenti**.

4.  In **ricerca utente**fare clic su **Cerca**e quindi su **Aggiungi filtro**.

5.  Nel criterio di ricerca selezionare **pool di registrazione**, selezionare **uguale a**, selezionare **FQDN corrente del pool**e quindi fare clic su **trova**.

6.  Nel menu **azione** fare clic su **Trasferisci tutti gli utenti in pool**.
    
    <div>
    

    > [!NOTE]  
    > Quando si applica un filtro a un set di utenti esistente, l'opzione <STRONG>trasferisce tutti gli utenti al pool</STRONG> si trova nel contesto del sottoinsieme filtrato degli utenti, non di <STRONG><EM>tutti</EM></STRONG> gli utenti possibili.

    
    </div>

7.  In **Move users**selezionare il pool che contiene gli account utente che si desidera trasferire nel **pool di registrazione di origine**.

8.  Nel **pool di registrar di destinazione**selezionare il pool in cui si desidera trasferire gli utenti.

9.  Opzionale Se il server o il pool di destinazione non è disponibile, selezionare la casella di controllo **forza** .
    
    <div>
    

    > [!Caution]  
    > Se si seleziona <STRONG>forza</STRONG>, l'account utente viene spostato, ma i dati utente associati tali conferenze e contatti pianificati non vengono spostati.

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>Per trasferire gli utenti da un pool a un altro usando i cmdlet di Windows PowerShell

1.  A seconda del modo in cui vengono eseguiti i comandi di Windows PowerShell, ovvero localmente o in remoto, è necessario accedere come membro dei ruoli amministrativi corretti di Lync Server 2013, come indicato di seguito:
    
    1.  Se si esegue i comandi nel computer locale, ad esempio si accede direttamente a un server front-end, accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in [autorizzazioni di configurazione delegate in Lync server 2013](lync-server-2013-delegate-setup-permissions.md).
    
    2.  Se si eseguono i comandi in remoto in un altro computer, ad esempio si accede al computer e si eseguono i comandi in remoto in un server front-end Standard Edition: da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator ruolo, accedere a qualsiasi computer della distribuzione interna.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Per trasferire singoli utenti, usare il cmdlet Move-CsUser come indicato di seguito:
    
        Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    
    Dove l'utente deve spostarsi è l'utente Pilar Ackerman e l'utente verrà spostato dal proprio pool di Home attualmente assegnato al pool pool01.contoso.net

4.  Per trasferire un numero elevato di utenti, usare i filtri con il cmdlet **Get-CsUser** e passare il set di utenti risultante a **Move-CsUser**:
    
        Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    
    I comandi combinati di **Get-CsUser** e **Move-CsUser** possono risultare in questo:
    
        Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Modifica delle proprietà dell'account utente in Lync Server 2013](lync-server-2013-modifying-user-account-properties.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

