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

# <a name="configure-user-account-settings-in-lync-server-2013"></a><span data-ttu-id="32397-102">Configurare le impostazioni degli account utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32397-102">Configure user account settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32397-103">_**Argomento Ultima modifica:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="32397-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="32397-104">Gli utenti con accesso esterno immettono il loro numero di telefono o l'estensione e un PIN per partecipare alle conferenze come utenti autenticati.</span><span class="sxs-lookup"><span data-stu-id="32397-104">Dial-in users enter their phone number or extension and a PIN to join conferences as authenticated users.</span></span> <span data-ttu-id="32397-105">L'URI della **linea** di telefonia specificato negli account utente di Lync Server è necessario per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="32397-105">The telephony **Line URI** specified on Lync Server user accounts is required for authentication.</span></span>

<span data-ttu-id="32397-106">La procedura descritta in questo argomento descrive come assegnare un **URI di linea** per un singolo account utente.</span><span class="sxs-lookup"><span data-stu-id="32397-106">The procedure in this topic describes how to assign a **Line URI** for a single user account.</span></span> <span data-ttu-id="32397-107">Se è necessario assegnare un **URI di linea** per più account utente, è possibile creare uno script che usa il cmdlet **Set-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="32397-107">If you need to assign a **Line URI** for multiple user accounts, you can create a script that uses the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="32397-108">Per informazioni dettagliate sull'uso di uno script di esempio per assegnare l' **URI di linea** a più account utente, vedere "assegnare URI di [http://go.microsoft.com/fwlink/p/?linkId=196945](http://go.microsoft.com/fwlink/p/?linkid=196945)linea a più utenti".</span><span class="sxs-lookup"><span data-stu-id="32397-108">For details about using a sample script to assign **Line URI** to multiple user accounts, see "Assign Line URIs to Multiple Users" at [http://go.microsoft.com/fwlink/p/?linkId=196945](http://go.microsoft.com/fwlink/p/?linkid=196945).</span></span>

<div>

## <a name="to-configure-user-account-settings"></a><span data-ttu-id="32397-109">Per configurare le impostazioni dell'account utente</span><span class="sxs-lookup"><span data-stu-id="32397-109">To configure user account settings</span></span>

1.  <span data-ttu-id="32397-110">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo **CS-UserAdministrator** o **CsAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="32397-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-UserAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="32397-111">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="32397-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="32397-112">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="32397-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="32397-113">Sulla barra di spostamento sinistra fare clic su **utenti**.</span><span class="sxs-lookup"><span data-stu-id="32397-113">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="32397-114">Nel campo di ricerca digitare il nome dell'utente che si vuole configurare per i servizi di conferenza telefonica con accesso esterno o fare clic su **Aggiungi filtro** per specificare i campi di ricerca e quindi fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="32397-114">In the search field, type the name of the user you want to configure for dial-in conferencing or click **Add filter** to specify search fields, and then click **Find**.</span></span>

5.  <span data-ttu-id="32397-115">Fare doppio clic sul nome utente per aprire la finestra di dialogo **modifica utente di Lync Server** .</span><span class="sxs-lookup"><span data-stu-id="32397-115">Double-click the user name to open the **Edit Lync Server User** dialog box.</span></span>

6.  <span data-ttu-id="32397-116">In **telefonia**, nel campo **URI di linea** digitare un numero di telefono normalizzato univoco, ad esempio Tel: + 14255550200.</span><span class="sxs-lookup"><span data-stu-id="32397-116">Under **Telephony**, in the **Line URI** field, type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="32397-117">Puoi specificare l' <STRONG>URI di linea</STRONG> solo se la <STRONG>telefonia</STRONG> è impostata solo su <STRONG>PC-to-PC</STRONG>, <STRONG>VoIP aziendale</STRONG>, <STRONG>controllo delle chiamate remote</STRONG> o <STRONG>controllo delle chiamate remote solo</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="32397-117">You can specify <STRONG>Line URI</STRONG> only if <STRONG>Telephony</STRONG> is set to <STRONG>PC-to-PC only</STRONG>, <STRONG>Enterprise Voice</STRONG>, <STRONG>Remote call control</STRONG> or <STRONG>Remote call control only</STRONG>.</span></span>

    
    </div>

7.  <span data-ttu-id="32397-118">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="32397-118">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

