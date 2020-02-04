---
title: 'Lync Server 2013: installazione di Lync per Windows Phone'
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
ms.openlocfilehash: 75e42f9fd2b954e943050fc9877706ae53a1143c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726136"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-lync-for-windows-phone-in-lync-server-2013"></a><span data-ttu-id="c3ec2-102">Installazione di Lync per Windows Phone in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3ec2-102">Installing Lync for Windows Phone in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3ec2-103">_**Argomento Ultima modifica:** 2014-02-03_</span><span class="sxs-lookup"><span data-stu-id="c3ec2-103">_**Topic Last Modified:** 2014-02-03_</span></span>

<span data-ttu-id="c3ec2-104">Lync 2013 per Windows Phone è un'applicazione installabile dall'utente disponibile in Windows Phone Marketplace.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-104">Lync 2013 for Windows Phone is a user-installable application that is available in the Windows Phone Marketplace.</span></span>

<div>

## <a name="installing-lync-for-windows-mobile"></a><span data-ttu-id="c3ec2-105">Installazione di Lync per Windows Mobile</span><span class="sxs-lookup"><span data-stu-id="c3ec2-105">Installing Lync for Windows Mobile</span></span>

<span data-ttu-id="c3ec2-106">Puoi richiedere agli utenti di installare Lync 2013 per Windows Phone nei propri dispositivi, indirizzando il computer a Windows Phone Marketplace <http://go.microsoft.com/fwlink/p/?linkid=231901>.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-106">You can instruct your users to install Lync 2013 for Windows Phone on their devices by directing them to the Windows Phone Marketplace at <http://go.microsoft.com/fwlink/p/?linkid=231901>.</span></span>

</div>

<div>

## <a name="if-you-use-a-dns-srv-record-to-publish-exchange-web-services"></a><span data-ttu-id="c3ec2-107">Se si usa un record SRV DNS per pubblicare i servizi Web di Exchange</span><span class="sxs-lookup"><span data-stu-id="c3ec2-107">If You Use a DNS SRV Record to Publish Exchange Web Services</span></span>

<span data-ttu-id="c3ec2-108">Per abilitare l'integrazione di Exchange per i client Lync, alcune organizzazioni pubblicano l'URL dei servizi Web Exchange usando un record SRV DNS.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-108">To enable Exchange integration for Lync clients, some organizations publish the Exchange Web Services URL by using a DNS SRV record.</span></span> <span data-ttu-id="c3ec2-109">Il documento "informazioni e risoluzione dei problemi di integrazione di Exchange", disponibile nell'area download [http://go.microsoft.com/fwlink/?LinkID=391095](http://go.microsoft.com/fwlink/?linkid=391095)Microsoft, descrive scenari in cui potrebbe essere necessario.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-109">The document "Understanding and Troubleshooting Exchange Integration," available in the Microsoft Download Center at [http://go.microsoft.com/fwlink/?LinkID=391095](http://go.microsoft.com/fwlink/?linkid=391095), describes scenarios in which this might be necessary.</span></span> <span data-ttu-id="c3ec2-110">Tuttavia, l'integrazione di Exchange per gli utenti di Windows Phone non funzionerà in questo scenario, perché la piattaforma Windows Phone non supporta le ricerche SRV.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-110">However, Exchange integration for Windows Phone users will not work in this scenario, because the Windows Phone platform does not support SRV lookups.</span></span> <span data-ttu-id="c3ec2-111">È necessario indicare agli utenti di Windows Phone di specificare l'URL dei servizi Web Exchange invece di consentire al telefono di rilevare automaticamente il server.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-111">You will need to instruct Windows Phone users to specify the Exchange Web Services URL instead of allowing the phone to automatically detect the server.</span></span>

<span data-ttu-id="c3ec2-112">Indica agli utenti di configurare le impostazioni di Lync nei loro telefoni Windows come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="c3ec2-112">Instruct your users to configure the Lync settings on their Windows Phones as follows:</span></span>

1.  <span data-ttu-id="c3ec2-113">In Windows Phone, nelle impostazioni di Lync, selezionare la schermata di **Exchange** .</span><span class="sxs-lookup"><span data-stu-id="c3ec2-113">In Windows Phone, in the Lync settings, select the **Exchange** screen.</span></span>

2.  <span data-ttu-id="c3ec2-114">Posizionare il **server di rilevamento automatico** su **disattivato**.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-114">Move **Auto-Detect Server** to **Off**.</span></span>

3.  <span data-ttu-id="c3ec2-115">Toccare il campo vuoto e immettere il nome di dominio completo (FQDN) o l'URL per i servizi Web Exchange.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-115">Tap the empty field and enter the fully qualified domain name (FQDN) or URL for Exchange Web Services.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c3ec2-116">È possibile specificare il nome di dominio completo (FQDN) o l'intero URL del server di Exchange Web Services.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-116">You can specify either the fully qualified domain name (FQDN) or the full URL of your Exchange Web Services server.</span></span> <span data-ttu-id="c3ec2-117">Se specifichi il nome di dominio completo, il protocollo (https://) e il percorso dei servizi Web di Exchange (/EWS/Exchange.asmx) vengono aggiunti automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-117">If you specify the FQDN, the protocol (https://) and the Exchange Web Services path (/ews/exchange.asmx) are added automatically.</span></span> <span data-ttu-id="c3ec2-118">Se il percorso dei servizi Web di Exchange è diverso, è possibile specificare l'URL completo.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-118">If your Exchange Web Services path is different, you can specify the full URL.</span></span>

    
    </div>

4.  <span data-ttu-id="c3ec2-119">Chiudere lo schermo.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-119">Close the screen.</span></span>

</div>

<div>

## <a name="verifying-mobile-client-installation"></a><span data-ttu-id="c3ec2-120">Verifica dell'installazione del client per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="c3ec2-120">Verifying Mobile Client Installation</span></span>

<span data-ttu-id="c3ec2-121">Dopo aver configurato il client e eseguito l'accesso, usare i test seguenti per verificare che l'installazione di Lync 2013 funzioni correttamente nel dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-121">After you configure the client and sign in successfully, use the following tests to verify that your installation of Lync 2013 is working correctly on your mobile device.</span></span>

<span data-ttu-id="c3ec2-122">**Cercare un contatto nella directory aziendale**</span><span class="sxs-lookup"><span data-stu-id="c3ec2-122">**Search for a contact in the corporate directory**</span></span>

1.  <span data-ttu-id="c3ec2-123">Nell'elenco contatti toccare **Cerca** nella parte inferiore.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-123">In the Contacts list, tap **Search** at the bottom.</span></span>

2.  <span data-ttu-id="c3ec2-124">Cercare un contatto esistente solo nell'elenco indirizzi globale.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-124">Search for a contact that exists only in the global address list.</span></span>

3.  <span data-ttu-id="c3ec2-125">Verificare che il nome del contatto venga visualizzato nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-125">Verify that the contact name appears in the search results.</span></span>

<span data-ttu-id="c3ec2-126">**Testare la messaggistica istantanea e la presenza**</span><span class="sxs-lookup"><span data-stu-id="c3ec2-126">**Test instant messaging and presence**</span></span>

1.  <span data-ttu-id="c3ec2-127">Nell'elenco contatti toccare un contatto.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-127">In the Contacts list, tap a contact.</span></span>

2.  <span data-ttu-id="c3ec2-128">Nella scheda contatto toccare l'icona **messaggistica istantanea** .</span><span class="sxs-lookup"><span data-stu-id="c3ec2-128">In the contact card, tap the **IM** icon.</span></span>

3.  <span data-ttu-id="c3ec2-129">Verificare che venga visualizzata una finestra di messaggistica istantanea (IM) e che sia possibile digitare e inviare un messaggio istantaneo.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-129">Verify that an instant messaging (IM) window appears and that you can type and send an IM.</span></span>

<span data-ttu-id="c3ec2-130">**Testare i servizi di conferenza telefonica con accesso esterno**</span><span class="sxs-lookup"><span data-stu-id="c3ec2-130">**Test dial-out conferencing**</span></span>

1.  <span data-ttu-id="c3ec2-131">In Outlook pianificare una riunione Lync.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-131">In Outlook, schedule a Lync meeting.</span></span>

2.  <span data-ttu-id="c3ec2-132">Nel dispositivo mobile aprire l'invito alla riunione.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-132">On the mobile device, open the meeting invitation.</span></span>

3.  <span data-ttu-id="c3ec2-133">Fare clic sul collegamento nella riunione per partecipare.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-133">Click the link in the meeting to join.</span></span>

4.  <span data-ttu-id="c3ec2-134">Rispondere alla chiamata dal servizio di conferenza e verificare che l'audio della riunione sia connesso.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-134">Answer the call from the conference service and verify that you are connected to meeting audio.</span></span>

<span data-ttu-id="c3ec2-135">**Verificare le notifiche push**</span><span class="sxs-lookup"><span data-stu-id="c3ec2-135">**Test push notifications**</span></span>

1.  <span data-ttu-id="c3ec2-136">Nel dispositivo mobile dell'utente, accedere a Lync con l'account dell'utente.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-136">On user A’s mobile device, sign in to Lync with user A’s account.</span></span>

2.  <span data-ttu-id="c3ec2-137">Aprire un'altra applicazione nel dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-137">Open another application on the mobile device.</span></span>

3.  <span data-ttu-id="c3ec2-138">In un altro client accedere a Lync con l'account dell'utente B.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-138">On a different client, sign in to Lync with user B’s account.</span></span>

4.  <span data-ttu-id="c3ec2-139">Inviare un messaggio istantaneo dall'utente B all'utente a.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-139">Send an IM from user B to user A.</span></span>

5.  <span data-ttu-id="c3ec2-140">Verificare che la notifica di messaggistica istantanea venga visualizzata nel dispositivo mobile dell'utente.</span><span class="sxs-lookup"><span data-stu-id="c3ec2-140">Verify that the IM notification appears on user A’s mobile device.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

