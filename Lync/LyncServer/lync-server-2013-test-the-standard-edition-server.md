---
title: 'Lync Server 2013: Testare il server Standard Edition'
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
ms.openlocfilehash: 00918643fcc59efc33d12dc3f8f77c7d3ac69815
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746056"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-standard-edition-server-in-lync-server-2013"></a>Testare il server Standard Edition in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-01_

La procedura seguente descrive come testare la distribuzione di un server Standard Edition.

<div>

## <a name="to-test-the-deployment-of-a-standard-edition-server"></a>Per testare la distribuzione di un server Standard Edition

1.  Usare i computer e gli utenti di Active Directory per aggiungere l'oggetto utente di Active Directory del ruolo di amministratore per la distribuzione di Lync Server 2013 (in cui è installato il pannello di controllo di Lync Server) nel gruppo **CsAdministrator** .

2.  Se l'oggetto utente è attualmente connesso, disconnettersi e quindi accedere di nuovo per registrare la nuova assegnazione del gruppo.
    
    <div>
    

    > [!NOTE]  
    > L'account utente non può essere l'amministratore locale del server in cui è in uso Lync Server 2013, Standard Edition. Se non si aggiungono gli utenti e i gruppi appropriati al gruppo CsAdministors, viene visualizzato un messaggio di errore quando si apre il pannello di controllo di Lync Server 2013, in cui viene indicato che "non autorizzato: Access viene negato a causa di un errore di autorizzazione del controllo di accesso basato sui ruoli".

    
    </div>

3.  Usare l'account amministrativo per accedere al computer in cui è installato il pannello di controllo di Lync Server.

4.  Avviare il pannello di controllo di Lync Server e specificare le credenziali, se richiesto. Il pannello di controllo di Lync Server 2013 Visualizza le informazioni sulla distribuzione.

5.  Nella barra di spostamento sinistra fare clic su **topologia**e quindi verificare che lo stato del servizio sia un'icona del computer con una freccia verde e sia presente un segno di spunta verde accanto a ogni ruolo di Lync Server Server distribuito e portato online.

6.  Nella barra di spostamento sinistra fare clic su **utenti**e quindi abilitare i due utenti per Lync Server 2013.

7.  È necessario registrare un utente in un computer collegato al dominio e l'altro utente in un altro computer del dominio.

8.  Installare Lync Server 2013 in ognuno dei due computer client e verificare che entrambi gli utenti possano accedere a Lync Server 2013 e inviare messaggi istantanei.

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

