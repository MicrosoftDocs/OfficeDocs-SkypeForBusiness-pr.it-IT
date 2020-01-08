---
title: 'Lync Server 2013: Configurare le impostazioni degli account utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure user account settings
ms:assetid: b7c74ecc-b924-4efc-8a56-3a5f94a9ef13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412896(v=OCS.15)
ms:contentKeyID: 48185200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4d06405d2f80aef5decb69d564ae399401d4328
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977975"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-user-account-settings-in-lync-server-2013"></a>Configurare le impostazioni degli account utente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-05_

Gli utenti con accesso esterno immettono il loro numero di telefono o l'estensione e un PIN per partecipare alle conferenze come utenti autenticati. L'URI della **linea** di telefonia specificato negli account utente di Lync Server è necessario per l'autenticazione.

La procedura descritta in questo argomento descrive come assegnare un **URI di linea** per un singolo account utente. Se è necessario assegnare un **URI di linea** per più account utente, è possibile creare uno script che usa il cmdlet **Set-CsUser** . Per informazioni dettagliate sull'uso di uno script di esempio per assegnare l' **URI di linea** a più account utente, vedere "assegnare URI di [http://go.microsoft.com/fwlink/p/?linkId=196945](http://go.microsoft.com/fwlink/p/?linkid=196945)linea a più utenti".

<div>

## <a name="to-configure-user-account-settings"></a>Per configurare le impostazioni dell'account utente

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo **CS-UserAdministrator** o **CsAdministrator** .

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **utenti**.

4.  Nel campo di ricerca digitare il nome dell'utente che si vuole configurare per i servizi di conferenza telefonica con accesso esterno o fare clic su **Aggiungi filtro** per specificare i campi di ricerca e quindi fare clic su **trova**.

5.  Fare doppio clic sul nome utente per aprire la finestra di dialogo **modifica utente di Lync Server** .

6.  In **telefonia**, nel campo **URI di linea** digitare un numero di telefono normalizzato univoco, ad esempio Tel: + 14255550200.
    
    <div>
    

    > [!NOTE]  
    > Puoi specificare l' <STRONG>URI di linea</STRONG> solo se la <STRONG>telefonia</STRONG> è impostata solo su <STRONG>PC-to-PC</STRONG>, <STRONG>VoIP aziendale</STRONG>, <STRONG>controllo delle chiamate remote</STRONG> o <STRONG>controllo delle chiamate remote solo</STRONG>.

    
    </div>

7.  Fare clic su **Commit**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

