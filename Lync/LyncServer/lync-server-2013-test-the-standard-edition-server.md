---
title: 'Lync Server 2013: testare il server Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the Standard Edition server
ms:assetid: b6ef67bb-9665-43e4-b8b3-eac8898eebf6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412890(v=OCS.15)
ms:contentKeyID: 48185220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26610b3619977413f3afa24027c7dfd757189a85
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-the-standard-edition-server-in-lync-server-2013"></a>Testare il server Standard Edition in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-01_

Nella procedura seguente viene descritto come testare la distribuzione di un server Standard Edition.

<div>

## <a name="to-test-the-deployment-of-a-standard-edition-server"></a>Per testare la distribuzione di un server Standard Edition

1.  Utilizzare computer e utenti di Active Directory per aggiungere l'oggetto utente di Active Directory del ruolo di amministratore per la distribuzione di Lync Server 2013 (in cui è installato il pannello di controllo di Lync Server) nel gruppo **CsAdministrator** .

2.  Se l'oggetto utente è connesso, disconnettersi e rieseguire l'accesso per registrare la nuova assegnazione al gruppo.
    
    <div>
    

    > [!NOTE]  
    > L'account utente non può essere l'amministratore locale del server che esegue Lync Server 2013, Standard Edition. Se non si aggiungono gli utenti e i gruppi corretti al gruppo CSAdministrator, verrà visualizzato un messaggio di errore durante l'apertura del pannello di controllo di Lync Server 2013, in cui viene indicato che "non autorizzato: accesso negato a causa di un errore di autorizzazione del controllo di accesso basato sui ruoli (RBAC)".

    
    </div>

3.  Utilizzare l'account amministrativo per accedere al computer in cui è installato il pannello di controllo di Lync Server.

4.  Avviare il pannello di controllo di Lync Server e fornire le credenziali, se richiesto. Il pannello di controllo di Lync Server 2013 Visualizza le informazioni sulla distribuzione.

5.  Sulla barra di spostamento sinistra fare clic su **topologia**e quindi verificare che lo stato del servizio sia un'icona del computer con una freccia verde e che sia presente un segno di spunta verde accanto a ogni ruolo del server Lync Server distribuito e portato online.

6.  Sulla barra di spostamento sinistra fare clic su **utenti**e quindi abilitare i due utenti per Lync Server 2013.

7.  Connettere un utente a un computer appartenente al dominio e l'altro utente a un altro computer nel dominio.

8.  Installare Lync Server 2013 in ognuno dei due computer client e quindi verificare che entrambi gli utenti siano in grado di accedere a Lync Server 2013 e possano inviare messaggi istantanei.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Distribuzione di client e dispositivi in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

