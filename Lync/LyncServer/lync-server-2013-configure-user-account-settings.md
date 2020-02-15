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
ms.openlocfilehash: 19bb9bbba1d9a247b2c33a4ae0fd95f9a8e4553a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-user-account-settings-in-lync-server-2013"></a><span data-ttu-id="706dc-102">Configurare le impostazioni degli account utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="706dc-102">Configure user account settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="706dc-103">_**Ultimo argomento modificato:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="706dc-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="706dc-104">Gli utenti connessi tramite chiamata in ingresso immettono il proprio numero di telefono o interno e un PIN per partecipare alle conferenze come utenti autenticati.</span><span class="sxs-lookup"><span data-stu-id="706dc-104">Dial-in users enter their phone number or extension and a PIN to join conferences as authenticated users.</span></span> <span data-ttu-id="706dc-105">L'URI della **linea** di telefonia specificata negli account utente di Lync Server è necessario per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="706dc-105">The telephony **Line URI** specified on Lync Server user accounts is required for authentication.</span></span>

<span data-ttu-id="706dc-106">Nella procedura illustrata in questo argomento viene descritto come assegnare un **URI linea** per un singolo account utente.</span><span class="sxs-lookup"><span data-stu-id="706dc-106">The procedure in this topic describes how to assign a **Line URI** for a single user account.</span></span> <span data-ttu-id="706dc-107">Se è necessario assegnare un **URI linea** per più account utente, è possibile creare uno script che utilizzi il cmdlet **Set-CsUser**.</span><span class="sxs-lookup"><span data-stu-id="706dc-107">If you need to assign a **Line URI** for multiple user accounts, you can create a script that uses the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="706dc-108">Per informazioni dettagliate sull'utilizzo di uno script di esempio per l'assegnazione di **URI di linea** a più account utente, vedere la sezione " [http://go.microsoft.com/fwlink/p/?linkId=196945](http://go.microsoft.com/fwlink/p/?linkid=196945)assegnare URI di linea a più utenti" all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="706dc-108">For details about using a sample script to assign **Line URI** to multiple user accounts, see "Assign Line URIs to Multiple Users" at [http://go.microsoft.com/fwlink/p/?linkId=196945](http://go.microsoft.com/fwlink/p/?linkid=196945).</span></span>

<div>

## <a name="to-configure-user-account-settings"></a><span data-ttu-id="706dc-109">Per configurare le impostazioni dell'account utente</span><span class="sxs-lookup"><span data-stu-id="706dc-109">To configure user account settings</span></span>

1.  <span data-ttu-id="706dc-110">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo **Cs-UserAdministrator** o **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="706dc-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-UserAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="706dc-111">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="706dc-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="706dc-112">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="706dc-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="706dc-113">Sulla barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="706dc-113">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="706dc-114">Nel campo di ricerca digitare il nome dell'utente che si desidera configurare per le conferenze telefoniche con accesso esterno oppure fare clic su **Aggiungi filtro** per specificare i campi di ricerca e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="706dc-114">In the search field, type the name of the user you want to configure for dial-in conferencing or click **Add filter** to specify search fields, and then click **Find**.</span></span>

5.  <span data-ttu-id="706dc-115">Fare doppio clic sul nome dell'utente per aprire la finestra di dialogo **modifica utente di Lync Server** .</span><span class="sxs-lookup"><span data-stu-id="706dc-115">Double-click the user name to open the **Edit Lync Server User** dialog box.</span></span>

6.  <span data-ttu-id="706dc-116">In **Telefonia**, nel campo **URI linea** digitare un numero di telefono normalizzato univoco, ad esempio tel:+14255550200).</span><span class="sxs-lookup"><span data-stu-id="706dc-116">Under **Telephony**, in the **Line URI** field, type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="706dc-117">È possibile specificare l' <STRONG>URI della linea</STRONG> solo se la funzionalità di <STRONG>telefonia</STRONG> è impostata solo su <STRONG>PC-a-PC</STRONG>, <STRONG>VoIP aziendale</STRONG>, <STRONG>controllo delle chiamate remote</STRONG> o <STRONG>controllo delle chiamate remote</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="706dc-117">You can specify <STRONG>Line URI</STRONG> only if <STRONG>Telephony</STRONG> is set to <STRONG>PC-to-PC only</STRONG>, <STRONG>Enterprise Voice</STRONG>, <STRONG>Remote call control</STRONG> or <STRONG>Remote call control only</STRONG>.</span></span>

    
    </div>

7.  <span data-ttu-id="706dc-118">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="706dc-118">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

