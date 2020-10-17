---
title: 'Lync Server 2013: spostare gli utenti in un altro pool'
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
ms.openlocfilehash: c4ecadb2a487dc17f18e1956b6ac075e25b0b035
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500553"
---
# <a name="move-users-to-another-pool-in-lync-server-2013"></a>Spostare gli utenti in un altro pool in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2018-02-09_

È possibile utilizzare il pannello di controllo di Lync Server per assegnare gli utenti a un server o un pool specifico.

<div>


> [!TIP]  
> Lo spostamento di tutti gli utenti esistenti da un pool di origine che esegue Lync Server 2010 o versione precedente in un pool di destinazione di Lync Server 2013 in un ambiente di Active Directory complesso potrebbe provocare una replica di Active Directory più lenta. Per evitare questo, è possibile utilizzare i filtri di ricerca per spostare gli utenti da pool che eseguono Lync Server 2010 o versioni precedenti separatamente oppure è possibile utilizzare Lync Server Management Shell per spostare gli utenti con i cmdlet. Inoltre, la funzionalità del filtro è compatibile con gli utenti di Lync Server 2013.



</div>

<div>

## <a name="to-move-selected-users-to-a-different-server-or-pool"></a>Per spostare un gruppo selezionato di utenti in un server o un pool diverso

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Utenti**.

4.  Nella casella **Cerca utenti** digitare anche solo la prima parte del nome visualizzato, nome, cognome, nome dell'account Gestione account di protezione, indirizzo SIP o URI (Uniform Resource Identifier (URI) di linea dell'account utente desiderato e quindi fare clic su **Trova**.

5.  Nell'elenco della tabella selezionare uno o più utenti specifici.

6.  Scegliere **Sposta utenti selezionati nel pool** dal menu **Azione**.

7.  In **Sposta utenti** selezionare il pool in cui spostare gli utenti in **Pool di registrazione di destinazione**.

8.  (Facoltativo) Se il server o il pool di destinazione non è disponibile, selezionare la casella di controllo **Forza**.
    
    <div>
    

    > [!Caution]  
    > Se si seleziona <STRONG>forza</STRONG>, l'account utente viene spostato, ma i dati utente associati tali conferenze e contatti pianificati non vengono spostati.

    
    </div>

</div>

<div>

## <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a>Per spostare tutti gli utenti da un server o un pool a un server o un pool diverso

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Utenti**.

4.  Scegliere **Sposta tutti gli utenti nel pool** dal menu **Azione**.

5.  In **Sposta utenti** selezionare il pool contenente gli account utente da spostare in **Pool di registrazione di origine**.

6.  In **Pool di registrazione di destinazione** selezionare il pool in cui spostare gli utenti.

7.  (Facoltativo) Se il server o il pool di destinazione non è disponibile, selezionare la casella di controllo **Forza**.
    
    <div>
    

    > [!Caution]  
    > Se si seleziona <STRONG>forza</STRONG>, l'account utente viene spostato, ma i dati utente associati tali conferenze e contatti pianificati non vengono spostati.

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a>Per spostare gli utenti da un pool a un altro mediante un filtro

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Utenti**.

4.  In **ricerca utente**fare clic su **Cerca**e quindi su **Aggiungi filtro**.

5.  Nei criteri di ricerca selezionare **Pool di registrazione**, **Uguale a**, **FQDN pool** e quindi fare clic su **Trova**.

6.  Scegliere **Sposta tutti gli utenti nel pool** dal menu **Azione**.
    
    <div>
    

    > [!NOTE]  
    > Quando un filtro viene applicato a un set di utenti esistente, l'opzione <STRONG>Sposta tutti gli utenti nel pool</STRONG> si trova nel contesto del sottoinsieme filtrato di utenti, non di <STRONG><EM>tutti</EM></STRONG> gli utenti possibili.

    
    </div>

7.  In **Sposta utenti** selezionare il pool contenente gli account utente da spostare in **Pool di registrazione di origine**.

8.  In **Pool di registrazione di destinazione** selezionare il pool in cui spostare gli utenti.

9.  (Facoltativo) Se il server o il pool di destinazione non è disponibile, selezionare la casella di controllo **Forza**.
    
    <div>
    

    > [!Caution]  
    > Se si seleziona <STRONG>forza</STRONG>, l'account utente viene spostato, ma i dati utente associati tali conferenze e contatti pianificati non vengono spostati.

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>Per spostare gli utenti da un pool a un altro utilizzando i cmdlet di Windows PowerShell

1.  A seconda di come vengono eseguiti i comandi di Windows PowerShell, ovvero localmente o in remoto, è necessario eseguire l'accesso come membri dei ruoli amministrativi di Lync Server 2013 corretti come indicato di seguito:
    
    1.  Se si eseguono i comandi nel computer locale, ad esempio si esegue l'accesso direttamente a un front end server, eseguire l'accesso al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in [delegate Setup Permissions in Lync server 2013](lync-server-2013-delegate-setup-permissions.md).
    
    2.  Se si eseguono i comandi in remoto in un altro computer (ad esempio, si accede al computer e si eseguono i comandi in remoto in un front end server Standard Edition): da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, eseguire l'accesso a qualsiasi computer nella distribuzione interna.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Per spostare singoli utenti, utilizzare il cmdlet Move-CsUser come indicato di seguito:
    
        Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    
    Dove l'utente da spostare si chiama Luisa Cazzaniga e verrà spostato dal pool principale assegnato al pool pool01.contoso.net

4.  Per spostare un numero elevato di utenti, utilizzare i filtri con il cmdlet **Get-CsUser** e passare il set di utenti risultanti a **Move-CsUser**:
    
        Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    
    La combinazione dei comandi di **Get-CsUser** e **Move-CsUser** può generare questo risultato:
    
        Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Modifica delle proprietà degli account utente in Lync Server 2013](lync-server-2013-modifying-user-account-properties.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

