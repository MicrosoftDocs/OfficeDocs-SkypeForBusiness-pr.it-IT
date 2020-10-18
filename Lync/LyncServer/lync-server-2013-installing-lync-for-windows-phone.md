---
title: 'Lync Server 2013: installazione di Lync per Windows Phone'
description: 'Lync Server 2013: installazione di Lync per Windows Phone.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Lync for Windows Phone
ms:assetid: bf502546-ff69-489f-a92e-a78b58803d53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690996(v=OCS.15)
ms:contentKeyID: 51541513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f5da90a5dc0babdc6944e4f9c426fe896d4f156
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573982"
---
# <a name="installing-lync-for-windows-phone-in-lync-server-2013"></a><span data-ttu-id="a6c6b-103">Installazione di Lync per Windows Phone in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6c6b-103">Installing Lync for Windows Phone in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6c6b-104">_**Ultimo argomento modificato:** 2014-02-03_</span><span class="sxs-lookup"><span data-stu-id="a6c6b-104">_**Topic Last Modified:** 2014-02-03_</span></span>

<span data-ttu-id="a6c6b-105">Lync 2013 per Windows Phone è un'applicazione installabile dall'utente disponibile nel Marketplace di Windows Phone.</span><span class="sxs-lookup"><span data-stu-id="a6c6b-105">Lync 2013 for Windows Phone is a user-installable application that is available in the Windows Phone Marketplace.</span></span>

<div>

## <a name="installing-lync-for-windows-mobile"></a><span data-ttu-id="a6c6b-106">Installazione di Lync per Windows Mobile</span><span class="sxs-lookup"><span data-stu-id="a6c6b-106">Installing Lync for Windows Mobile</span></span>

<span data-ttu-id="a6c6b-107">È possibile indicare agli utenti di installare Lync 2013 per Windows Phone sui propri dispositivi, indirizzati a Windows Phone Marketplace all'indirizzo <https://go.microsoft.com/fwlink/p/?linkid=231901> .</span><span class="sxs-lookup"><span data-stu-id="a6c6b-107">You can instruct your users to install Lync 2013 for Windows Phone on their devices by directing them to the Windows Phone Marketplace at <https://go.microsoft.com/fwlink/p/?linkid=231901>.</span></span>

</div>

<div>

## <a name="if-you-use-a-dns-srv-record-to-publish-exchange-web-services"></a><span data-ttu-id="a6c6b-108">Se si utilizza un record DNS SRV per pubblicare i servizi Web di Exchange</span><span class="sxs-lookup"><span data-stu-id="a6c6b-108">If You Use a DNS SRV Record to Publish Exchange Web Services</span></span>

<span data-ttu-id="a6c6b-109">Per abilitare l'integrazione di Exchange per i client Lync, alcune organizzazioni pubblicano l'URL dei servizi Web di Exchange utilizzando un record DNS SRV.</span><span class="sxs-lookup"><span data-stu-id="a6c6b-109">To enable Exchange integration for Lync clients, some organizations publish the Exchange Web Services URL by using a DNS SRV record.</span></span> <span data-ttu-id="a6c6b-110">Il documento "informazioni e risoluzione dei problemi relativi all'integrazione di Exchange", disponibile nell'area download Microsoft [https://go.microsoft.com/fwlink/?LinkID=391095](https://go.microsoft.com/fwlink/?linkid=391095) , descrive gli scenari in cui potrebbe essere necessario.</span><span class="sxs-lookup"><span data-stu-id="a6c6b-110">The document "Understanding and Troubleshooting Exchange Integration," available in the Microsoft Download Center at [https://go.microsoft.com/fwlink/?LinkID=391095](https://go.microsoft.com/fwlink/?linkid=391095), describes scenarios in which this might be necessary.</span></span> <span data-ttu-id="a6c6b-111">Tuttavia, l'integrazione di Exchange per gli utenti di Windows Phone non funzionerà in questo scenario, poiché la piattaforma Windows Phone non supporta le ricerche SRV.</span><span class="sxs-lookup"><span data-stu-id="a6c6b-111">However, Exchange integration for Windows Phone users will not work in this scenario, because the Windows Phone platform does not support SRV lookups.</span></span> <span data-ttu-id="a6c6b-112">Sarà necessario indicare agli utenti di Windows Phone di specificare l'URL dei servizi Web di Exchange anziché consentire al telefono di rilevare automaticamente il server.</span><span class="sxs-lookup"><span data-stu-id="a6c6b-112">You will need to instruct Windows Phone users to specify the Exchange Web Services URL instead of allowing the phone to automatically detect the server.</span></span>

<span data-ttu-id="a6c6b-113">Indicare agli utenti di configurare le impostazioni di Lync nei rispettivi telefoni Windows, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a6c6b-113">Instruct your users to configure the Lync settings on their Windows Phones as follows:</span></span>

1.  <span data-ttu-id="a6c6b-114">In Windows Phone, nelle impostazioni di Lync, selezionare la schermata di **Exchange** .</span><span class="sxs-lookup"><span data-stu-id="a6c6b-114">In Windows Phone, in the Lync settings, select the **Exchange** screen.</span></span>

2.  <span data-ttu-id="a6c6b-115">Spostare il **server di rilevamento automatico** su **disattivato**.</span><span class="sxs-lookup"><span data-stu-id="a6c6b-115">Move **Auto-Detect Server** to **Off**.</span></span>

3.  <span data-ttu-id="a6c6b-116">Toccare il campo vuoto e immettere il nome di dominio completo (FQDN) o l'URL per i servizi Web di Exchange.</span><span class="sxs-lookup"><span data-stu-id="a6c6b-116">Tap the empty field and enter the fully qualified domain name (FQDN) or URL for Exchange Web Services.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a6c6b-117">È possibile specificare il nome di dominio completo (FQDN) o l'URL completo del server di servizi Web Exchange.</span><span class="sxs-lookup"><span data-stu-id="a6c6b-117">You can specify either the fully qualified domain name (FQDN) or the full URL of your Exchange Web Services server.</span></span> <span data-ttu-id="a6c6b-118">Se si specifica il nome di dominio completo, il protocollo (https://) e il percorso dei servizi Web di Exchange (/EWS/Exchange.asmx) vengono aggiunti automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a6c6b-118">If you specify the FQDN, the protocol (https://) and the Exchange Web Services path (/ews/exchange.asmx) are added automatically.</span></span> <span data-ttu-id="a6c6b-119">Se il percorso dei servizi Web Exchange è diverso, è possibile specificare l'URL completo.</span><span class="sxs-lookup"><span data-stu-id="a6c6b-119">If your Exchange Web Services path is different, you can specify the full URL.</span></span>

    
    </div>

4.  <span data-ttu-id="a6c6b-120">Chiudere lo schermo.</span><span class="sxs-lookup"><span data-stu-id="a6c6b-120">Close the screen.</span></span>

</div>

<div>

## <a name="verifying-mobile-client-installation"></a><span data-ttu-id="a6c6b-121">Verifica dell'installazione del client mobile</span><span class="sxs-lookup"><span data-stu-id="a6c6b-121">Verifying Mobile Client Installation</span></span>

<span data-ttu-id="a6c6b-122">Dopo aver configurato il client e aver eseguito l'accesso, utilizzare i test seguenti per verificare che l'installazione di Lync 2013 funzioni correttamente sul dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="a6c6b-122">After you configure the client and sign in successfully, use the following tests to verify that your installation of Lync 2013 is working correctly on your mobile device.</span></span>

<span data-ttu-id="a6c6b-123">**Cercare un contatto nella directory aziendale**</span><span class="sxs-lookup"><span data-stu-id="a6c6b-123">**Search for a contact in the corporate directory**</span></span>

1.  <span data-ttu-id="a6c6b-124">Nell'elenco Contatti toccare **Cerca** in basso.</span><span class="sxs-lookup"><span data-stu-id="a6c6b-124">In the Contacts list, tap **Search** at the bottom.</span></span>

2.  <span data-ttu-id="a6c6b-125">Cercare un contatto presente solo nell'elenco indirizzi globale.</span><span class="sxs-lookup"><span data-stu-id="a6c6b-125">Search for a contact that exists only in the global address list.</span></span>

3.  <span data-ttu-id="a6c6b-126">Verificare che il nome del contatto sia incluso nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="a6c6b-126">Verify that the contact name appears in the search results.</span></span>

<span data-ttu-id="a6c6b-127">**Testare la messaggistica istantanea e la presenza**</span><span class="sxs-lookup"><span data-stu-id="a6c6b-127">**Test instant messaging and presence**</span></span>

1.  <span data-ttu-id="a6c6b-128">Toccare un contatto nell'elenco contatti.</span><span class="sxs-lookup"><span data-stu-id="a6c6b-128">In the Contacts list, tap a contact.</span></span>

2.  <span data-ttu-id="a6c6b-129">Nella scheda del contatto toccare l'icona **Messaggistica istantanea**.</span><span class="sxs-lookup"><span data-stu-id="a6c6b-129">In the contact card, tap the **IM** icon.</span></span>

3.  <span data-ttu-id="a6c6b-130">Verificare che venga visualizzata una finestra di messaggistica istantanea e che sia possibile digitare e inviare un messaggio istantaneo.</span><span class="sxs-lookup"><span data-stu-id="a6c6b-130">Verify that an instant messaging (IM) window appears and that you can type and send an IM.</span></span>

<span data-ttu-id="a6c6b-131">**Testare le funzionalità di conferenza telefonica con accesso esterno**</span><span class="sxs-lookup"><span data-stu-id="a6c6b-131">**Test dial-out conferencing**</span></span>

1.  <span data-ttu-id="a6c6b-132">In Outlook, pianificare una riunione di Lync.</span><span class="sxs-lookup"><span data-stu-id="a6c6b-132">In Outlook, schedule a Lync meeting.</span></span>

2.  <span data-ttu-id="a6c6b-133">Aprire l'invito alla riunione nel dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="a6c6b-133">On the mobile device, open the meeting invitation.</span></span>

3.  <span data-ttu-id="a6c6b-134">Fare clic sul collegamento nell'invito per partecipare alla riunione.</span><span class="sxs-lookup"><span data-stu-id="a6c6b-134">Click the link in the meeting to join.</span></span>

4.  <span data-ttu-id="a6c6b-135">Rispondere alla chiamata dal servizio di conferenza e verificare di essere connessi all'audio della riunione.</span><span class="sxs-lookup"><span data-stu-id="a6c6b-135">Answer the call from the conference service and verify that you are connected to meeting audio.</span></span>

<span data-ttu-id="a6c6b-136">**Verificare le notifiche push**</span><span class="sxs-lookup"><span data-stu-id="a6c6b-136">**Test push notifications**</span></span>

1.  <span data-ttu-id="a6c6b-137">Nel dispositivo mobile dell'utente A accedere a Lync con l'account dell'utente A.</span><span class="sxs-lookup"><span data-stu-id="a6c6b-137">On user A’s mobile device, sign in to Lync with user A’s account.</span></span>

2.  <span data-ttu-id="a6c6b-138">Aprire un'altra applicazione nel dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="a6c6b-138">Open another application on the mobile device.</span></span>

3.  <span data-ttu-id="a6c6b-139">In un altro client, accedere a Lync con l'account dell'utente B.</span><span class="sxs-lookup"><span data-stu-id="a6c6b-139">On a different client, sign in to Lync with user B’s account.</span></span>

4.  <span data-ttu-id="a6c6b-140">Inviare un messaggio istantaneo dall'utente B all'utente A.</span><span class="sxs-lookup"><span data-stu-id="a6c6b-140">Send an IM from user B to user A.</span></span>

5.  <span data-ttu-id="a6c6b-141">Verificare che la notifica di messaggio istantaneo venga visualizzata nel dispositivo mobile dell'utente A.</span><span class="sxs-lookup"><span data-stu-id="a6c6b-141">Verify that the IM notification appears on user A’s mobile device.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

