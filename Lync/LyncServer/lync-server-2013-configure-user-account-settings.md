---
title: 'Lync Server 2013: configurare le impostazioni degli account utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure user account settings
ms:assetid: b7c74ecc-b924-4efc-8a56-3a5f94a9ef13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412896(v=OCS.15)
ms:contentKeyID: 48185200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1b3c8ea077b6dee724d131ea117aa7bf304e114
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196889"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-user-account-settings-in-lync-server-2013"></a>Configurare le impostazioni degli account utente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-05_

Gli utenti connessi tramite chiamata in ingresso immettono il proprio numero di telefono o interno e un PIN per partecipare alle conferenze come utenti autenticati. L'URI della **linea** di telefonia specificata negli account utente di Lync Server è necessario per l'autenticazione.

Nella procedura illustrata in questo argomento viene descritto come assegnare un **URI linea** per un singolo account utente. Se è necessario assegnare un **URI linea** per più account utente, è possibile creare uno script che utilizzi il cmdlet **Set-CsUser**. Per informazioni dettagliate sull'utilizzo di uno script di esempio per l'assegnazione di **URI di linea** a più account utente, vedere la sezione " [https://go.microsoft.com/fwlink/p/?linkId=196945](https://go.microsoft.com/fwlink/p/?linkid=196945)assegnare URI di linea a più utenti" all'indirizzo.

<div>

## <a name="to-configure-user-account-settings"></a>Per configurare le impostazioni dell'account utente

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo **Cs-UserAdministrator** o **CsAdministrator**.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Utenti**.

4.  Nel campo di ricerca digitare il nome dell'utente che si desidera configurare per le conferenze telefoniche con accesso esterno oppure fare clic su **Aggiungi filtro** per specificare i campi di ricerca e quindi fare clic su **Trova**.

5.  Fare doppio clic sul nome dell'utente per aprire la finestra di dialogo **modifica utente di Lync Server** .

6.  In **Telefonia**, nel campo **URI linea** digitare un numero di telefono normalizzato univoco, ad esempio tel:+14255550200).
    
    <div>
    

    > [!NOTE]  
    > È possibile specificare l' <STRONG>URI della linea</STRONG> solo se la funzionalità di <STRONG>telefonia</STRONG> è impostata solo su <STRONG>PC-a-PC</STRONG>, <STRONG>VoIP aziendale</STRONG>, <STRONG>controllo delle chiamate remote</STRONG> o <STRONG>controllo delle chiamate remote</STRONG>.

    
    </div>

7.  Fare clic su **Commit**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

