---
title: "Lync Server 2013: verificare l'accesso tramite il proxy inverso"
description: "Lync Server 2013: verificare l'accesso tramite il proxy inverso."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify access through your reverse proxy
ms:assetid: 3076a786-e022-4d41-91ec-1bf252b2a468
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429697(v=OCS.15)
ms:contentKeyID: 48183753
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 593aac5574f0dcf683351f12a6392f6116480ac5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547122"
---
# <a name="verify-access-through-your-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="35e3a-103">Verificare l'accesso tramite il proxy inverso in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35e3a-103">Verify access through your reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35e3a-104">_**Ultimo argomento modificato:** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="35e3a-104">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="35e3a-p101">Eseguire la procedura seguente per verificare che gli utenti possano accedere alle informazioni nel proxy inverso. Potrebbe essere necessario completare la configurazione del firewall e la configurazione di DNS (Domain Name System) prima che l'accesso funzioni correttamente.</span><span class="sxs-lookup"><span data-stu-id="35e3a-p101">Use the following procedure to verify that your users can access information on the reverse proxy. You might need to complete the firewall configuration and Domain Name System (DNS) configuration before access will work correctly.</span></span>

<div>

## <a name="to-verify-that-you-can-access-the-website-through-the-internet"></a><span data-ttu-id="35e3a-107">Per verificare che sia possibile accedere al sito Web tramite Internet</span><span class="sxs-lookup"><span data-stu-id="35e3a-107">To verify that you can access the website through the Internet</span></span>

  - <span data-ttu-id="35e3a-108">Aprire un Web browser, digitare nella barra\*\*\*\* degli indirizzi gli URL utilizzati dai client per accedere ai file della Rubrica e al sito Web per le conferenze, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="35e3a-108">Open a web browser, type the URLs in the **Address** bar that clients use to access the Address Book files and the website for conferencing as follows:</span></span>
    
      - <span data-ttu-id="35e3a-109">Per il server della Rubrica, digitare un URL analogo al seguente: **https://externalwebfarmFQDN/abs** dove FQDNWebfarmesterna è il nome di dominio completo esterno dei servizi Web esterni che ospita i servizi Rubrica.</span><span class="sxs-lookup"><span data-stu-id="35e3a-109">For Address Book Server, type a URL similar to the following: **https://externalwebfarmFQDN/abs** where externalwebfarmFQDN is the external FQDN of the external web services that hosts Address Book services.</span></span> <span data-ttu-id="35e3a-110">L'utente deve ricevere una richiesta di verifica HTTP, poiché la sicurezza delle directory nella cartella del server della Rubrica è configurata per l'uso dell'autenticazione di Windows per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="35e3a-110">The user should receive an HTTP challenge, because directory security on the Address Book Server folder is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="35e3a-111">Per le conferenze, digitare un URL analogo al seguente: **https://externalwebfarmFQDN/meet** dove FQDNWebfarmesterna è il nome di dominio completo esterno della Web farm che ospita il contenuto della riunione.</span><span class="sxs-lookup"><span data-stu-id="35e3a-111">For conferencing, type a URL similar to the following: **https://externalwebfarmFQDN/meet** where externalwebfarmFQDN is the external FQDN of the web farm that hosts meeting content.</span></span> <span data-ttu-id="35e3a-112">Questo URL dovrebbe visualizzare la pagina di risoluzione dei problemi per le conferenze.</span><span class="sxs-lookup"><span data-stu-id="35e3a-112">This URL should display the troubleshooting page for conferencing.</span></span> <span data-ttu-id="35e3a-113">In alternativa, confermare che l'URL semplice per le funzioni di conferenza funzioni correttamente.</span><span class="sxs-lookup"><span data-stu-id="35e3a-113">Alternatively, confirm that your Simple URL for conferencing functions correctly.</span></span> <span data-ttu-id="35e3a-114">Un esempio di URL semplice per la conferenza join potrebbe essere https://meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="35e3a-114">An example Simple URL for the conference join might be https://meet.contoso.com</span></span>
    
      - <span data-ttu-id="35e3a-115">Per l'espansione del gruppo di distribuzione, digitare un URL simile al seguente: **https://externalwebfarmFQDN/GroupExpansion/service.svc** .</span><span class="sxs-lookup"><span data-stu-id="35e3a-115">For distribution group expansion, type a URL similar to the following: **https://externalwebfarmFQDN/GroupExpansion/service.svc**.</span></span> <span data-ttu-id="35e3a-116">L'utente dovrebbe ricevere una richiesta di verifica HTTP, poiché la sicurezza delle directory nel servizio di espansione dei gruppi di distribuzione è configurata per l'utilizzo dell'autenticazione di Windows per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="35e3a-116">The user should receive an HTTP challenge, because directory security on the distribution group expansion service is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="35e3a-117">Per l'accesso esterno, digitare l'URL semplice, analogo al seguente, in **https://externalwebfarmFQDN/dialin** cui FQDNWebfarmesterna è il nome di dominio completo esterni della Web farm in cui è ospitata la pagina di chiamata in accesso esterno per le conferenze telefoniche con accesso interno.</span><span class="sxs-lookup"><span data-stu-id="35e3a-117">For dial-in, type the simple URL similar to the following **https://externalwebfarmFQDN/dialin** where externalwebfarmFQDN is the external FQDN of the web farm that hosts the dial-in page for dial-in conferencing.</span></span> <span data-ttu-id="35e3a-118">L'utente deve essere indirizzato alla pagina di accesso remoto.</span><span class="sxs-lookup"><span data-stu-id="35e3a-118">The user should be directed to the dial-in page.</span></span> <span data-ttu-id="35e3a-119">In alternativa, confermare che l'URL semplice per l'accesso remoto funzioni correttamente.</span><span class="sxs-lookup"><span data-stu-id="35e3a-119">Alternatively, confirm that your Simple URL dial-in functions correctly.</span></span> <span data-ttu-id="35e3a-120">Un esempio di URL semplice per l'accesso esterno può essere https://dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="35e3a-120">An example Simple URL for dial-in might be https://dialin.contoso.com</span></span>
    
      - <span data-ttu-id="35e3a-121">Per verificare che l'URL di individuazione automatica funzioni, digitare https://lyncdiscover .</span><span class="sxs-lookup"><span data-stu-id="35e3a-121">To confirm that the autodiscover URL is working, type https://lyncdiscover.</span></span> <span data-ttu-id="35e3a-122">externaldomainFQDN.</span><span class="sxs-lookup"><span data-stu-id="35e3a-122">externaldomainFQDN.</span></span> <span data-ttu-id="35e3a-123">Il browser dovrebbe richiedere l'apertura di un file.</span><span class="sxs-lookup"><span data-stu-id="35e3a-123">The browser should prompt you to open a file.</span></span> <span data-ttu-id="35e3a-124">Selezionare Blocco note per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="35e3a-124">Select Notepad to open it.</span></span> <span data-ttu-id="35e3a-125">Una risposta tipica sarebbe simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="35e3a-125">A typical response would be similar to:</span></span>
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

</div>

</div>

<span> </span>

</div>

</div>

</div>

