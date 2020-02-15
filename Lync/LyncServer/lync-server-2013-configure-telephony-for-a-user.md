---
title: 'Lync Server 2013: configurare la telefonia per un utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure telephony for a user
ms:assetid: 4546432e-c839-4517-a2c5-bc0d4d8c6a03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520988(v=OCS.15)
ms:contentKeyID: 48183987
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cac7f13d7ba46b9affee1f4d44dd56b167597b80
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043258"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-telephony-for-a-user-in-lync-server-2013"></a><span data-ttu-id="54c0d-102">Configurare la telefonia per un utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54c0d-102">Configure telephony for a user in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54c0d-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="54c0d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="54c0d-104">Le impostazioni di telefonia sono alcune delle singole impostazioni di un account utente che possono essere configurate nel pannello di controllo di Lync Server per l'utente, ovvero se il singolo utente è stato abilitato per Lync Server 2013 e l'organizzazione supporta la telefonia.</span><span class="sxs-lookup"><span data-stu-id="54c0d-104">Telephony settings are some of the individual settings of a user account that can be configured in Lync Server Control Panel for the user (that is, if the individual user has been enabled for Lync Server 2013 and the organization supports telephony).</span></span>

<span data-ttu-id="54c0d-105">Le opzioni di telefonia utente di Lync Server includono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="54c0d-105">Lync Server user telephony options include the following:</span></span>

  - <span data-ttu-id="54c0d-106">**Audio/video disabilitato**   l'utente non può effettuare chiamate con audio e video.</span><span class="sxs-lookup"><span data-stu-id="54c0d-106">**Audio/video disabled**   The user cannot make calls with audio and video.</span></span>

  - <span data-ttu-id="54c0d-107">**Da PC a PC solo**   l'utente può effettuare solo chiamate audio o video da PC a PC.</span><span class="sxs-lookup"><span data-stu-id="54c0d-107">**PC-to-PC only**   The user can make only PC-to-PC audio or video calls.</span></span>

  - <span data-ttu-id="54c0d-108">**VoIP aziendale l'**   utente può utilizzare l'infrastruttura di Lync Server 2013 per instradare tutte le chiamate in ingresso e in uscita.</span><span class="sxs-lookup"><span data-stu-id="54c0d-108">**Enterprise Voice**   The user can use the Lync Server 2013 infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="54c0d-109">Può inoltre effettuare chiamate da PC a PC.</span><span class="sxs-lookup"><span data-stu-id="54c0d-109">The user can also make PC-to-PC calls.</span></span>

  - <span data-ttu-id="54c0d-110">**Controllo delle chiamate remote**   l'utente può utilizzare Lync Server 2013 per controllare il telefono desktop e può anche effettuare chiamate da PC a PC.</span><span class="sxs-lookup"><span data-stu-id="54c0d-110">**Remote call control**   The user can use Lync Server 2013 to control the desktop phone, and can also make PC-to-PC calls.</span></span>

<span data-ttu-id="54c0d-111">Per informazioni dettagliate sulla configurazione della telefonia per un'organizzazione, vedere [configurare la telefonia per un utente in Lync server 2013](lync-server-2013-configure-telephony-for-a-user.md) e [distribuzione di VoIP aziendale in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="54c0d-111">For details about configuring telephony for an organization, see [Configure telephony for a user in Lync Server 2013](lync-server-2013-configure-telephony-for-a-user.md) and [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span>

<div>

## <a name="to-configure-telephony-for-a-specific-user-account"></a><span data-ttu-id="54c0d-112">Per configurare la telefonia per un account utente specifico</span><span class="sxs-lookup"><span data-stu-id="54c0d-112">To configure telephony for a specific user account</span></span>

1.  <span data-ttu-id="54c0d-113">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="54c0d-113">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="54c0d-114">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="54c0d-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="54c0d-115">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="54c0d-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="54c0d-116">Sulla barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="54c0d-116">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="54c0d-117">Nella casella **Ricerca utenti** digitare interamente o parzialmente il nome visualizzato, il nome, il cognome, il nome account del sistema degli account di sicurezza (SAM), l'indirizzo SIP o l'URI (Uniform Resource Identifier) linea dell'account utente desiderato e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="54c0d-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>

5.  <span data-ttu-id="54c0d-118">Nella tabella fare clic sull'account utente che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="54c0d-118">In the table, click the user account that you want to modify.</span></span>

6.  <span data-ttu-id="54c0d-119">Scegliere **Modifica** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="54c0d-119">On the **Edit** menu, click **Modify**.</span></span>

7.  <span data-ttu-id="54c0d-120">In **Telefonia** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="54c0d-120">In **Telephony**, do the following:</span></span>
    
      - <span data-ttu-id="54c0d-121">Per disabilitare le chiamate audio e le videochiamate per l'utente, fare clic su **Audio/video disabilitati**.</span><span class="sxs-lookup"><span data-stu-id="54c0d-121">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
      - <span data-ttu-id="54c0d-p103">Per abilitare le comunicazioni audio da PC a PC per l'utente, ma non il controllo delle chiamate remote o VoIP aziendale, fare clic su **Solo da PC a PC**. Specificare un valore per **URI linea** per il telefono utilizzato dall'utente per le comunicazioni audio da PC a PC.</span><span class="sxs-lookup"><span data-stu-id="54c0d-p103">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**. Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
      - <span data-ttu-id="54c0d-124">Per instradare le chiamate telefoniche dell'utente utilizzando l'infrastruttura di Lync Server 2010 in base alla classe dei criteri di servizio, incluse le comunicazioni audio da PC a PC, fare clic su **VoIP aziendale**.</span><span class="sxs-lookup"><span data-stu-id="54c0d-124">To route the user's phone calls by using the Lync Server 2010 infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="54c0d-125">In **URI linea** specificare il numero di telefono per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="54c0d-125">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="54c0d-126">In **Criteri dial plan** e **Criteri vocali** specificare i criteri appropriati per l'utente.</span><span class="sxs-lookup"><span data-stu-id="54c0d-126">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="54c0d-127">Per specificare le regole di normalizzazione per la conversione dei numeri di telefono composti dall'utente nel formato E.164, selezionare il profilo località appropriato in **Criteri percorso**.</span><span class="sxs-lookup"><span data-stu-id="54c0d-127">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
      - <span data-ttu-id="54c0d-128">Per abilitare il controllo delle chiamate remote, che consente agli utenti di controllare la linea telefonica desktop da Lync Server 2013 per effettuare chiamate da PC a PC e chiamate da PC a telefono, fare clic su **Remote Call Control**.</span><span class="sxs-lookup"><span data-stu-id="54c0d-128">To enable remote call control, which enables users to control their desktop phone line from Lync Server 2013 to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="54c0d-129">In **URI linea** specificare il numero di telefono per il controllo delle chiamate remote.</span><span class="sxs-lookup"><span data-stu-id="54c0d-129">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="54c0d-130">L'utente deve disporre di un telefono da scrivania e di una connessione PBX per il routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="54c0d-130">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="54c0d-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54c0d-131">See Also</span></span>


[<span data-ttu-id="54c0d-132">Modifica delle proprietà degli account utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54c0d-132">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

