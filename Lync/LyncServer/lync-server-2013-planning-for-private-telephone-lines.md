---
title: 'Lync Server 2013: pianificazione per le linee telefoniche private'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for private telephone lines
ms:assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412728(v=OCS.15)
ms:contentKeyID: 48184909
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4287e4b80b146e26fe5e548c07e5df189b1960e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978882"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-private-telephone-lines-with-lync-server-2013"></a><span data-ttu-id="ec45e-102">Pianificazione per le linee telefoniche private con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ec45e-102">Planning for private telephone lines with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec45e-103">_**Argomento Ultima modifica:** 2013-02-11_</span><span class="sxs-lookup"><span data-stu-id="ec45e-103">_**Topic Last Modified:** 2013-02-11_</span></span>

<span data-ttu-id="ec45e-104">Lync Server 2013 introduce la possibilità di fornire agli utenti una seconda linea telefonica privata oltre alla propria linea telefonica principale.</span><span class="sxs-lookup"><span data-stu-id="ec45e-104">Lync Server 2013 introduces the ability to give users a second, private telephone line in addition to their primary telephone line.</span></span> <span data-ttu-id="ec45e-105">Le linee telefoniche private sono spesso assegnate a dirigenti e ad altri che desiderano un numero di telefono non in elenco a cui possono essere raggiunti direttamente.</span><span class="sxs-lookup"><span data-stu-id="ec45e-105">Private telephone lines are often assigned to executives and others who want an unlisted telephone number at which they can be reached directly.</span></span>

<span data-ttu-id="ec45e-106">Le linee telefoniche private possono essere configurate solo con Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ec45e-106">Private telephone lines can only be configured with the Lync Server Management Shell.</span></span> <span data-ttu-id="ec45e-107">Non è possibile configurare le linee telefoniche private con il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ec45e-107">You cannot configure private telephone lines with the Lync Server Control Panel.</span></span> <span data-ttu-id="ec45e-108">Le linee telefoniche private devono essere configurate solo nelle distribuzioni di Lync Server e non in distribuzioni miste.</span><span class="sxs-lookup"><span data-stu-id="ec45e-108">Private telephone lines should be configured only in deployments of Lync Server and not in mixed deployments.</span></span>

<div>

## <a name="characteristics-of-private-telephone-lines"></a><span data-ttu-id="ec45e-109">Caratteristiche delle linee telefoniche private</span><span class="sxs-lookup"><span data-stu-id="ec45e-109">Characteristics of Private Telephone Lines</span></span>

<span data-ttu-id="ec45e-110">Anche se il concetto di una seconda linea telefonica privata è fondamentalmente semplice, è importante comprendere le caratteristiche delle linee private e i modi in cui sono simili e diversi dalle linee telefoniche primarie degli utenti.</span><span class="sxs-lookup"><span data-stu-id="ec45e-110">Although the concept of a second, private telephone line is fundamentally simple, it is important to understand the characteristics of private lines and the ways in which they are similar to and different from users’ primary telephone lines.</span></span>

<div>

## <a name="general-characteristics-of-private-telephone-lines"></a><span data-ttu-id="ec45e-111">Caratteristiche generali delle linee telefoniche private</span><span class="sxs-lookup"><span data-stu-id="ec45e-111">General Characteristics of Private Telephone Lines</span></span>

  - <span data-ttu-id="ec45e-112">Un utente può avere una sola linea telefonica privata.</span><span class="sxs-lookup"><span data-stu-id="ec45e-112">A user can have only one private telephone line.</span></span>

  - <span data-ttu-id="ec45e-113">Un utente con una linea telefonica privata ha una sola cassetta postale vocale e riceve le notifiche delle chiamate perse in un singolo indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="ec45e-113">A user with a private telephone line has only one voice mailbox and receives missed call notifications at a single email address.</span></span>

  - <span data-ttu-id="ec45e-114">Un utente con una linea telefonica privata non ha un secondo indirizzo SIP e una seconda linea telefonica privata non fornisce a un utente una seconda presenza nella rete, ad esempio una seconda identità di messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="ec45e-114">A user with a private telephone line does not have a second SIP address, and a second, private telephone line does not give a user a second presence on the network (such as a second instant messaging identity).</span></span>

  - <span data-ttu-id="ec45e-115">Le linee telefoniche private sono disponibili solo per le distribuzioni locali.</span><span class="sxs-lookup"><span data-stu-id="ec45e-115">Private telephone lines are available for on-premises deployments only.</span></span> <span data-ttu-id="ec45e-116">Non sono disponibili con distribuzioni ospitate di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ec45e-116">They are not available with hosted deployments of Lync Server.</span></span>

</div>

<div>

## <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a><span data-ttu-id="ec45e-117">Come le linee telefoniche private differiscono dalle linee telefoniche primarie</span><span class="sxs-lookup"><span data-stu-id="ec45e-117">How Private Telephone Lines Differ from Primary Telephone Lines</span></span>

  - <span data-ttu-id="ec45e-118">I numeri di telefono per le linee telefoniche private non vengono visualizzati nelle directory telefoniche o negli elenchi di contatti derivati da servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ec45e-118">The telephone numbers for private telephone lines do not appear in the telephone directories or Contacts lists that are derived from Active Directory Domain Services.</span></span>

  - <span data-ttu-id="ec45e-119">Nessuna delle caratteristiche seguenti è disponibile con una linea telefonica privata: inoltro di chiamata, chiamata del team, delega, anello del team, prelievo delle chiamate di gruppo e applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="ec45e-119">None of the following features are available with a private telephone line: call forwarding, team call, delegation, team ring, Group Call Pickup, and Response Group application.</span></span>

  - <span data-ttu-id="ec45e-120">Le chiamate a una linea telefonica privata hanno un anello speciale e la notifica di sistema per la chiamata indica all'utente che la chiamata in arrivo si trova nella propria linea privata.</span><span class="sxs-lookup"><span data-stu-id="ec45e-120">Calls to a private telephone line have a special ring, and the system notification for the call tells the user that the incoming call is on his or her private line.</span></span>

  - <span data-ttu-id="ec45e-121">Le chiamate alla linea telefonica privata squillano sempre.</span><span class="sxs-lookup"><span data-stu-id="ec45e-121">Calls to the private telephone line always ring through.</span></span> <span data-ttu-id="ec45e-122">Non seguono le regole "non disturbare".</span><span class="sxs-lookup"><span data-stu-id="ec45e-122">They do not follow "do not disturb" rules.</span></span>

  - <span data-ttu-id="ec45e-123">Le linee telefoniche private sono solo in ingresso e non possono essere usate per effettuare chiamate in uscita.</span><span class="sxs-lookup"><span data-stu-id="ec45e-123">Private telephone lines are inbound only and cannot be used to make outgoing calls.</span></span> <span data-ttu-id="ec45e-124">Quando un utente con una linea telefonica privata effettua una chiamata, la chiamata proviene dalla linea telefonica principale dell'utente e non nasconde il nome dell'utente o il numero di telefono principale dell'utente dalla persona chiamata.</span><span class="sxs-lookup"><span data-stu-id="ec45e-124">When a user with a private telephone line makes a call, the call originates from the user’s primary telephone line and does not hide the user’s name or the user’s primary telephone number from the person called.</span></span>

</div>

<div>

## <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a><span data-ttu-id="ec45e-125">Come le linee telefoniche private sono simili alle linee telefoniche primarie</span><span class="sxs-lookup"><span data-stu-id="ec45e-125">How Private Telephone Lines Are Similar to Primary Telephone Lines</span></span>

  - <span data-ttu-id="ec45e-126">Le chiamate senza risposta a una linea telefonica privata vengono instradate alla stessa posta in arrivo della segreteria telefonica, se è abilitata la casella vocale.</span><span class="sxs-lookup"><span data-stu-id="ec45e-126">Unanswered calls to a private telephone line are routed to the same voice mail inbox as for the primary telephone line (if voice mail is enabled).</span></span>

  - <span data-ttu-id="ec45e-127">Chiamare il pick-up e chiamare il lavoro pickup con le linee telefoniche private nello stesso modo che fanno con la linea telefonica principale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="ec45e-127">Call park and call pickup work with private telephone lines in exactly the same manner as they do with the user’s primary telephone line.</span></span>

  - <span data-ttu-id="ec45e-128">Quando è abilitata la chiamata simultanea sulla linea telefonica primaria di un utente, è abilitata anche nella linea telefonica privata.</span><span class="sxs-lookup"><span data-stu-id="ec45e-128">When simultaneous ringing is enabled on a user’s primary telephone line, it is also enabled on the private telephone line.</span></span>

  - <span data-ttu-id="ec45e-129">Il numero di telefono di una linea telefonica privata viene registrato nel record dettagli chiamata nello stesso modo in cui è indicato il numero di telefono della linea telefonica principale di un utente, ma con l'indicazione che si tratta di un numero di telefono privato.</span><span class="sxs-lookup"><span data-stu-id="ec45e-129">The telephone number for a private telephone line is recorded in the call detail record in the same manner as the telephone number for a user’s primary telephone line, but with an indication that it is a private telephone number.</span></span>

  - <span data-ttu-id="ec45e-130">Dopo che un utente risponde a una chiamata su una linea telefonica privata, la chiamata viene trattata come una chiamata nella linea telefonica principale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="ec45e-130">After a user answers a call on a private telephone line, the call is treated the same as a call on the user’s primary telephone line.</span></span> <span data-ttu-id="ec45e-131">Ad esempio, se un utente che riceve una chiamata su una linea telefonica privata inoltra la chiamata o invita altre persone a una chiamata in conferenza, il nome dell'utente viene visualizzato in Lync 2013 e il numero di telefono della linea telefonica principale dell'utente viene visualizzato nell'ID chiamante.</span><span class="sxs-lookup"><span data-stu-id="ec45e-131">For example, if a user who receives a call on a private telephone line forwards the call or invites others to a conference call, the user’s name appears in Lync 2013, and the telephone number for the user’s primary telephone line appears in caller ID.</span></span>

  - <span data-ttu-id="ec45e-132">Un utente può deviare una chiamata (reindirizza la chiamata a un'altra destinazione, ad esempio un cellulare o il telefono di casa, prima di rispondere) dalla linea telefonica privata nello stesso modo con una linea telefonica principale.</span><span class="sxs-lookup"><span data-stu-id="ec45e-132">A user can deflect a call (redirect the call to another destination, such as a mobile phone or home phone, before answering) from the private telephone line in the same manner as with a primary telephone line.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ec45e-133">Quando una chiamata a una riga privata viene instradata a un numero di telefono alternativo, il numero di telefono della linea telefonica privata viene reso disponibile al numero di telefono alternativo e può essere visualizzato nei registri per il numero.</span><span class="sxs-lookup"><span data-stu-id="ec45e-133">When a call to a private line is routed to an alternate telephone number, the telephone number for the private telephone line is made available to the alternate telephone number and can be displayed in the logs for that number.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ec45e-134">Le chiamate da una conferenza alla linea telefonica privata non avranno un'indicazione a <EM>linee private</EM> nella notifica del sistema in arrivo.</span><span class="sxs-lookup"><span data-stu-id="ec45e-134">Calls from a conference to the private telephone line will not have a <EM>private-line</EM> indication in the incoming system notification.</span></span>

    
    </div>

</div>

</div>

<div>

## <a name="administering-private-telephone-lines"></a><span data-ttu-id="ec45e-135">Amministrazione di linee telefoniche private</span><span class="sxs-lookup"><span data-stu-id="ec45e-135">Administering Private Telephone Lines</span></span>

<span data-ttu-id="ec45e-136">Oltre agli aspetti tecnici della creazione e della gestione di linee telefoniche private, è necessario stabilire le procedure amministrative.</span><span class="sxs-lookup"><span data-stu-id="ec45e-136">In addition to the technical aspects of creating and managing private telephone lines, you will need to establish administrative procedures for them.</span></span> <span data-ttu-id="ec45e-137">Ciò include la determinazione dei criteri per chi è idoneo per una linea privata, la creazione e la manutenzione di elenchi di persone e le relative linee telefoniche, eventualmente la creazione di una directory telefonica privata per i dirigenti, l'organizzazione di formazione per gli utenti e attività correlate.</span><span class="sxs-lookup"><span data-stu-id="ec45e-137">This includes determining policies for who in the organization is eligible for a private line, creating and maintaining lists of people and their telephone lines, possibly creating a private telephone directory for executives, arranging for user training, and related tasks.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ec45e-138">La linea telefonica privata viene archiviata in Active Directory come attributo msRTCSIP-PrivateLine per l'oggetto utente.</span><span class="sxs-lookup"><span data-stu-id="ec45e-138">The private telephone line is stored in Active Directory as an msRTCSIP-PrivateLine attribute on the user object.</span></span> <span data-ttu-id="ec45e-139">Per impostazione predefinita, un membro del gruppo Authenticated Users ha accesso in lettura a questo attributo.</span><span class="sxs-lookup"><span data-stu-id="ec45e-139">By default any member of the Authenticated Users group has read access to this attribute.</span></span>



</div>

<div>

## <a name="assigning-telephone-numbers"></a><span data-ttu-id="ec45e-140">Assegnazione di numeri di telefono</span><span class="sxs-lookup"><span data-stu-id="ec45e-140">Assigning Telephone Numbers</span></span>

<span data-ttu-id="ec45e-141">Gli account per i nuovi utenti che hanno bisogno di linee telefoniche private vengono creati allo stesso modo degli account senza linee telefoniche private, usando il pannello di controllo di Lync Server o Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ec45e-141">Accounts for new users who need private telephone lines are created in the same manner as accounts without private telephone lines, using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<span data-ttu-id="ec45e-142">Utilizzare il cmdlet **Set-CsUser** in Lync Server Management Shell per assegnare un numero di telefono a una linea telefonica privata per un utente, ad esempio **Set-CsUser-Identity "SIP:Joe@contoso.com"-PrivateLine "Tel: + 14255551212"**.</span><span class="sxs-lookup"><span data-stu-id="ec45e-142">Use the **Set-CsUser** cmdlet in the Lync Server Management Shell to assign a telephone number to a private telephone line for a user, for example, **Set-CsUser -Identity "sip:joe@contoso.com" -PrivateLine "Tel:+14255551212"**.</span></span>

<span data-ttu-id="ec45e-143">I numeri di telefono per le linee telefoniche private possono avere una lunghezza compresa tra 3 e 15 numeri e devono essere preceduti dal prefisso "TEL:".</span><span class="sxs-lookup"><span data-stu-id="ec45e-143">Telephone numbers for private telephone lines can be between 3 and 15 numbers in length and must be preceded with the "TEL:" prefix.</span></span> <span data-ttu-id="ec45e-144">Possono avere qualsiasi prefisso locale e qualsiasi codice di paese o area geografica purché l'organizzazione disponga di una chiamata diretta verso l'interno per il codice area e il codice paese/area geografica.</span><span class="sxs-lookup"><span data-stu-id="ec45e-144">They can have any area code and any country/region code as long as your organization has direct inward dialing for that area code and country/region code.</span></span>

<span data-ttu-id="ec45e-145">Per informazioni dettagliate sui cmdlet e Lync Server Management Shell, vedere la documentazione di [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) .</span><span class="sxs-lookup"><span data-stu-id="ec45e-145">For details about cmdlets and Lync Server Management Shell, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

<div>

## <a name="private-telephone-lines-in-mixed-deployments"></a><span data-ttu-id="ec45e-146">Linee telefoniche private in distribuzioni miste</span><span class="sxs-lookup"><span data-stu-id="ec45e-146">Private Telephone Lines in Mixed Deployments</span></span>

<span data-ttu-id="ec45e-147">Le linee telefoniche private devono essere configurate solo per le distribuzioni di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ec45e-147">Private telephone lines should be configured only for deployments of Lync Server.</span></span> <span data-ttu-id="ec45e-148">In una distribuzione in cui sono presenti sia Lync Server che Office Communications Server 2007 o Office Communications Server 2007 R2 Server, quando un utente della versione precedente tenta di chiamare una linea telefonica privata, il routing della chiamata non riesce perché il server non può eseguire una ricerca in numero inverso su una linea telefonica privata.</span><span class="sxs-lookup"><span data-stu-id="ec45e-148">In a deployment in which there are both Lync Server and Office Communications Server 2007 or Office Communications Server 2007 R2 servers, when a user on earlier version attempts to call a private telephone line, routing of the call fails because the server cannot perform a reverse number lookup on a private telephone line.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

