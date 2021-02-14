---
title: Pianificare le linee telefoniche private con Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
description: Pianificazione di linee telefoniche private (secondarie) in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 0ae62c4ee56a16583106c89b5ca1b190ee242e2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813596"
---
# <a name="plan-for-private-telephone-lines-with-skype-for-business"></a><span data-ttu-id="9ab10-103">Pianificare le linee telefoniche private con Skype for Business</span><span class="sxs-lookup"><span data-stu-id="9ab10-103">Plan for private telephone lines with Skype for Business</span></span>
 
<span data-ttu-id="9ab10-104">Pianificazione di linee telefoniche private (secondarie) in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="9ab10-104">Planning for private (secondary) telephone lines in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="9ab10-105">Skype for Business Server consente di fornire agli utenti una seconda linea telefonica privata oltre alla linea telefonica principale.</span><span class="sxs-lookup"><span data-stu-id="9ab10-105">Skype for Business Server enables you to give users a second, private telephone line in addition to their primary telephone line.</span></span> <span data-ttu-id="9ab10-106">Le linee telefoniche private vengono spesso assegnate ai dirigenti e ad altri che desiderano un numero di telefono non in elenco al quale possono essere raggiunte direttamente.</span><span class="sxs-lookup"><span data-stu-id="9ab10-106">Private telephone lines are often assigned to executives and others who want an unlisted telephone number at which they can be reached directly.</span></span>
  
<span data-ttu-id="9ab10-107">Le linee telefoniche private possono essere configurate solo con Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9ab10-107">Private telephone lines can only be configured with the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="9ab10-108">Non è possibile configurare linee telefoniche private con il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9ab10-108">You cannot configure private telephone lines with the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="9ab10-109">Le linee telefoniche private devono essere configurate solo nelle distribuzioni di Skype for Business Server e non nelle distribuzioni miste.</span><span class="sxs-lookup"><span data-stu-id="9ab10-109">Private telephone lines should be configured only in deployments of Skype for Business Server and not in mixed deployments.</span></span>
  
## <a name="characteristics-of-private-telephone-lines"></a><span data-ttu-id="9ab10-110">Caratteristiche delle linee telefoniche private</span><span class="sxs-lookup"><span data-stu-id="9ab10-110">Characteristics of Private Telephone Lines</span></span>

<span data-ttu-id="9ab10-111">Sebbene il concetto di una seconda linea telefonica privata sia fondamentalmente semplice, è importante comprendere le caratteristiche delle linee private e i modi in cui sono simili e diverse dalle linee telefoniche principali degli utenti.</span><span class="sxs-lookup"><span data-stu-id="9ab10-111">Although the concept of a second, private telephone line is fundamentally simple, it is important to understand the characteristics of private lines and the ways in which they are similar to and different from users' primary telephone lines.</span></span>
  
### <a name="general-characteristics-of-private-telephone-lines"></a><span data-ttu-id="9ab10-112">Caratteristiche generali delle linee telefoniche private</span><span class="sxs-lookup"><span data-stu-id="9ab10-112">General Characteristics of Private Telephone Lines</span></span>

- <span data-ttu-id="9ab10-113">Un utente può disporre di una sola linea telefonica privata.</span><span class="sxs-lookup"><span data-stu-id="9ab10-113">A user can have only one private telephone line.</span></span>
    
- <span data-ttu-id="9ab10-114">Un utente con una linea telefonica privata dispone di una sola cassetta postale vocale e riceve notifiche di chiamata senza risposta in un singolo indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="9ab10-114">A user with a private telephone line has only one voice mailbox and receives missed call notifications at a single email address.</span></span>
    
- <span data-ttu-id="9ab10-115">Un utente con una linea telefonica privata non dispone di un secondo indirizzo SIP e una seconda linea telefonica privata non assegna a un utente una seconda presenza sulla rete, ad esempio una seconda identità di messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="9ab10-115">A user with a private telephone line does not have a second SIP address, and a second, private telephone line does not give a user a second presence on the network (such as a second instant messaging identity).</span></span> 
    
- <span data-ttu-id="9ab10-116">Le linee telefoniche private sono disponibili solo per le distribuzioni locali.</span><span class="sxs-lookup"><span data-stu-id="9ab10-116">Private telephone lines are available for on-premises deployments only.</span></span> <span data-ttu-id="9ab10-117">Non sono disponibili con le distribuzioni ospitate di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9ab10-117">They are not available with hosted deployments of Skype for Business Server.</span></span>
    
### <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a><span data-ttu-id="9ab10-118">Differenze tra le linee telefoniche private e le linee telefoniche primarie</span><span class="sxs-lookup"><span data-stu-id="9ab10-118">How Private Telephone Lines Differ from Primary Telephone Lines</span></span>

- <span data-ttu-id="9ab10-119">I numeri di telefono per le linee telefoniche private non vengono visualizzati nelle directory telefoniche o negli elenchi contatti derivati da Servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9ab10-119">The telephone numbers for private telephone lines do not appear in the telephone directories or Contacts lists that are derived from Active Directory Domain Services.</span></span>
    
- <span data-ttu-id="9ab10-120">Nessuna delle seguenti funzionalità è disponibile con una linea telefonica privata: inoltro di chiamata, chiamata del team, delega, anello del team, risposta alle chiamate di gruppo e applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="9ab10-120">None of the following features are available with a private telephone line: call forwarding, team call, delegation, team ring, Group Call Pickup, and Response Group application.</span></span>
    
- <span data-ttu-id="9ab10-121">Le chiamate a una linea telefonica privata hanno un anello speciale e la notifica di sistema per la chiamata indica all'utente che la chiamata in arrivo è sulla sua linea privata.</span><span class="sxs-lookup"><span data-stu-id="9ab10-121">Calls to a private telephone line have a special ring, and the system notification for the call tells the user that the incoming call is on his or her private line.</span></span>
    
- <span data-ttu-id="9ab10-122">Le chiamate alla linea telefonica privata squillano sempre.</span><span class="sxs-lookup"><span data-stu-id="9ab10-122">Calls to the private telephone line always ring through.</span></span> <span data-ttu-id="9ab10-123">Non seguono le regole "non disturbare".</span><span class="sxs-lookup"><span data-stu-id="9ab10-123">They do not follow "do not disturb" rules.</span></span>
    
- <span data-ttu-id="9ab10-124">Le linee telefoniche private sono solo in ingresso e non possono essere utilizzate per effettuare chiamate in uscita.</span><span class="sxs-lookup"><span data-stu-id="9ab10-124">Private telephone lines are inbound only and cannot be used to make outgoing calls.</span></span> <span data-ttu-id="9ab10-125">Quando un utente con una linea telefonica privata effettua una chiamata, la chiamata ha origine dalla linea telefonica principale dell'utente e non nasconde il nome dell'utente o il numero di telefono principale dell'utente dalla persona chiamata.</span><span class="sxs-lookup"><span data-stu-id="9ab10-125">When a user with a private telephone line makes a call, the call originates from the user's primary telephone line and does not hide the user's name or the user's primary telephone number from the person called.</span></span>
    
### <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a><span data-ttu-id="9ab10-126">Analogie tra le linee telefoniche private e le linee telefoniche primarie</span><span class="sxs-lookup"><span data-stu-id="9ab10-126">How Private Telephone Lines Are Similar to Primary Telephone Lines</span></span>

- <span data-ttu-id="9ab10-127">Le chiamate senza risposta a una linea telefonica privata vengono instradate alla stessa posta in arrivo della segreteria telefonica della linea telefonica principale (se la segreteria telefonica è abilitata).</span><span class="sxs-lookup"><span data-stu-id="9ab10-127">Unanswered calls to a private telephone line are routed to the same voice mail inbox as for the primary telephone line (if voice mail is enabled).</span></span>
    
- <span data-ttu-id="9ab10-128">Il parcheggio di chiamata e la risposta alle chiamate funzionano con le linee telefoniche private esattamente come con la linea telefonica principale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="9ab10-128">Call park and call pickup work with private telephone lines in exactly the same manner as they do with the user's primary telephone line.</span></span>
    
- <span data-ttu-id="9ab10-129">Quando lo squillo simultaneo è abilitato sulla linea telefonica principale di un utente, viene abilitato anche sulla linea telefonica privata.</span><span class="sxs-lookup"><span data-stu-id="9ab10-129">When simultaneous ringing is enabled on a user's primary telephone line, it is also enabled on the private telephone line.</span></span>
    
- <span data-ttu-id="9ab10-130">Il numero di telefono di una linea telefonica privata viene registrato nel record dettagli chiamata allo stesso modo del numero di telefono della linea telefonica principale di un utente, ma con l'indicazione che si tratta di un numero di telefono privato.</span><span class="sxs-lookup"><span data-stu-id="9ab10-130">The telephone number for a private telephone line is recorded in the call detail record in the same manner as the telephone number for a user's primary telephone line, but with an indication that it is a private telephone number.</span></span>
    
- <span data-ttu-id="9ab10-131">Dopo che un utente risponde a una chiamata su una linea telefonica privata, la chiamata viene trattata come una chiamata sulla linea telefonica principale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="9ab10-131">After a user answers a call on a private telephone line, the call is treated the same as a call on the user's primary telephone line.</span></span> <span data-ttu-id="9ab10-132">Ad esempio, se un utente che riceve una chiamata su una linea telefonica privata inoltra la chiamata o invita altri utenti a una conferenza telefonica, il nome dell'utente viene visualizzato in Skype for Business e il numero di telefono della linea telefonica principale dell'utente viene visualizzato nell'ID chiamante.</span><span class="sxs-lookup"><span data-stu-id="9ab10-132">For example, if a user who receives a call on a private telephone line forwards the call or invites others to a conference call, the user's name appears in Skype for Business, and the telephone number for the user's primary telephone line appears in caller ID.</span></span>
    
- <span data-ttu-id="9ab10-133">Un utente può deviare una chiamata (reindirizzare la chiamata a un'altra destinazione, ad esempio un cellulare o un telefono dell'abitazione, prima di rispondere) dalla linea telefonica privata allo stesso modo di una linea telefonica principale.</span><span class="sxs-lookup"><span data-stu-id="9ab10-133">A user can deflect a call (redirect the call to another destination, such as a mobile phone or home phone, before answering) from the private telephone line in the same manner as with a primary telephone line.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="9ab10-134">Quando una chiamata a una linea privata viene instradata a un numero di telefono alternativo, il numero di telefono della linea telefonica privata viene reso disponibile per il numero di telefono alternativo e può essere visualizzato nei registri di tale numero.</span><span class="sxs-lookup"><span data-stu-id="9ab10-134">When a call to a private line is routed to an alternate telephone number, the telephone number for the private telephone line is made available to the alternate telephone number and can be displayed in the logs for that number.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="9ab10-135">Le chiamate da una conferenza alla linea telefonica privata non avranno un'indicazione  *di*  linea privata nella notifica del sistema in arrivo.</span><span class="sxs-lookup"><span data-stu-id="9ab10-135">Calls from a conference to the private telephone line will not have a  *private-line*  indication in the incoming system notification.</span></span>
  
## <a name="administering-private-telephone-lines"></a><span data-ttu-id="9ab10-136">Amministrazione delle linee telefoniche private</span><span class="sxs-lookup"><span data-stu-id="9ab10-136">Administering Private Telephone Lines</span></span>

<span data-ttu-id="9ab10-137">Oltre agli aspetti tecnici relativi alla creazione e alla gestione delle linee telefoniche private, è necessario stabilire procedure amministrative per le linee telefoniche.</span><span class="sxs-lookup"><span data-stu-id="9ab10-137">In addition to the technical aspects of creating and managing private telephone lines, you will need to establish administrative procedures for them.</span></span> <span data-ttu-id="9ab10-138">Ciò include la determinazione dei criteri per chi nell'organizzazione è idoneo per una linea privata, la creazione e la gestione di elenchi di persone e delle loro linee telefoniche, la creazione di una directory telefonica privata per i dirigenti, l'organizzazione per la formazione degli utenti e le attività correlate.</span><span class="sxs-lookup"><span data-stu-id="9ab10-138">This includes determining policies for who in the organization is eligible for a private line, creating and maintaining lists of people and their telephone lines, possibly creating a private telephone directory for executives, arranging for user training, and related tasks.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9ab10-139">La linea telefonica privata viene archiviata in Active Directory come attributo msRTCSIP-PrivateLine nell'oggetto utente.</span><span class="sxs-lookup"><span data-stu-id="9ab10-139">The private telephone line is stored in Active Directory as an msRTCSIP-PrivateLine attribute on the user object.</span></span> <span data-ttu-id="9ab10-140">Per impostazione predefinita, qualsiasi membro del gruppo Authenticated Users dispone dell'accesso in lettura a questo attributo.</span><span class="sxs-lookup"><span data-stu-id="9ab10-140">By default any member of the Authenticated Users group has read access to this attribute.</span></span> 
  
### <a name="assigning-telephone-numbers"></a><span data-ttu-id="9ab10-141">Assegnazione di numeri di telefono</span><span class="sxs-lookup"><span data-stu-id="9ab10-141">Assigning Telephone Numbers</span></span>

 <span data-ttu-id="9ab10-142">Gli account per i nuovi utenti che necessitano di linee telefoniche private vengono creati come gli account senza linee telefoniche private, utilizzando il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9ab10-142">Accounts for new users who need private telephone lines are created in the same manner as accounts without private telephone lines, using Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="9ab10-143">Utilizzare il cmdlet **Set-CsUser** in Skype for Business Server Management Shell per assegnare un numero di telefono a una linea telefonica privata per un utente, ad esempio **Set-CsUser -Identity "sip:joe@contoso.com" -PrivateLine "Tel:+14255551212"**.</span><span class="sxs-lookup"><span data-stu-id="9ab10-143">Use the **Set-CsUser** cmdlet in the Skype for Business Server Management Shell to assign a telephone number to a private telephone line for a user, for example, **Set-CsUser -Identity "sip:joe@contoso.com" -PrivateLine "Tel:+14255551212"**.</span></span>
  
<span data-ttu-id="9ab10-144">I numeri di telefono per le linee telefoniche private possono avere una lunghezza compresa tra 3 e 15 e devono essere preceduti dal prefisso "TEL:".</span><span class="sxs-lookup"><span data-stu-id="9ab10-144">Telephone numbers for private telephone lines can be between 3 and 15 numbers in length and must be preceded with the "TEL:" prefix.</span></span> <span data-ttu-id="9ab10-145">Possono avere qualsiasi codice di area geografica e qualsiasi codice paese, purché l'organizzazione abbia una composizione diretta verso l'interno per tale codice di area geografica e paese.</span><span class="sxs-lookup"><span data-stu-id="9ab10-145">They can have any area code and any country/region code as long as your organization has direct inward dialing for that area code and country/region code.</span></span> 
  
<span data-ttu-id="9ab10-146">Per informazioni dettagliate sui cmdlet e Skype for Business Server Management Shell, vedere la documentazione di Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9ab10-146">For details about cmdlets and Skype for Business Server Management Shell, see the Skype for Business Server Management Shell documentation.</span></span>
  
### <a name="private-telephone-lines-in-mixed-deployments"></a><span data-ttu-id="9ab10-147">Linee telefoniche private nelle distribuzioni miste</span><span class="sxs-lookup"><span data-stu-id="9ab10-147">Private Telephone Lines in Mixed Deployments</span></span>

<span data-ttu-id="9ab10-148">Le linee telefoniche private devono essere configurate solo per le distribuzioni di Skype for Business Server o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9ab10-148">Private telephone lines should be configured only for deployments of Skype for Business Server or Lync Server 2013.</span></span> <span data-ttu-id="9ab10-149">In una distribuzione in cui sono presenti server che eseguono versioni precedenti di Lync Server, quando un utente con una versione precedente tenta di chiamare una linea telefonica privata, l'instradamento della chiamata non riesce perché il server non è in grado di eseguire una ricerca di numeri inversa su una linea telefonica privata.</span><span class="sxs-lookup"><span data-stu-id="9ab10-149">In a deployment in which there are servers running earlier versions of Lync Server, when a user on earlier version attempts to call a private telephone line, routing of the call fails because the server cannot perform a reverse number lookup on a private telephone line.</span></span>
  

