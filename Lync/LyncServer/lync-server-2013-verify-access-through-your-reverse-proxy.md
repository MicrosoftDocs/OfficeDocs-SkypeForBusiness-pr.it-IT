---
title: "Lync Server 2013: verificare l'accesso tramite il proxy inverso"
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
ms.openlocfilehash: 8b8c8e4c92f0cdb9eb1b7070735882b43a308080
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518713"
---
# <a name="verify-access-through-your-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="7152c-102">Verificare l'accesso tramite il proxy inverso in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7152c-102">Verify access through your reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7152c-103">_**Ultimo argomento modificato:** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="7152c-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="7152c-p101">Eseguire la procedura seguente per verificare che gli utenti possano accedere alle informazioni nel proxy inverso. Potrebbe essere necessario completare la configurazione del firewall e la configurazione di DNS (Domain Name System) prima che l'accesso funzioni correttamente.</span><span class="sxs-lookup"><span data-stu-id="7152c-p101">Use the following procedure to verify that your users can access information on the reverse proxy. You might need to complete the firewall configuration and Domain Name System (DNS) configuration before access will work correctly.</span></span>

<div>

## <a name="to-verify-that-you-can-access-the-website-through-the-internet"></a><span data-ttu-id="7152c-106">Per verificare che sia possibile accedere al sito Web tramite Internet</span><span class="sxs-lookup"><span data-stu-id="7152c-106">To verify that you can access the website through the Internet</span></span>

  - <span data-ttu-id="7152c-107">Aprire un Web browser, digitare nella barra\*\*\*\* degli indirizzi gli URL utilizzati dai client per accedere ai file della Rubrica e al sito Web per le conferenze, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="7152c-107">Open a web browser, type the URLs in the **Address** bar that clients use to access the Address Book files and the website for conferencing as follows:</span></span>
    
      - <span data-ttu-id="7152c-108">Per il server della Rubrica, digitare un URL analogo al seguente: **https://externalwebfarmFQDN/abs** dove FQDNWebfarmesterna è il nome di dominio completo esterno dei servizi Web esterni che ospita i servizi Rubrica.</span><span class="sxs-lookup"><span data-stu-id="7152c-108">For Address Book Server, type a URL similar to the following: **https://externalwebfarmFQDN/abs** where externalwebfarmFQDN is the external FQDN of the external web services that hosts Address Book services.</span></span> <span data-ttu-id="7152c-109">L'utente deve ricevere una richiesta di verifica HTTP, poiché la sicurezza delle directory nella cartella del server della Rubrica è configurata per l'uso dell'autenticazione di Windows per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="7152c-109">The user should receive an HTTP challenge, because directory security on the Address Book Server folder is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="7152c-110">Per le conferenze, digitare un URL analogo al seguente: **https://externalwebfarmFQDN/meet** dove FQDNWebfarmesterna è il nome di dominio completo esterno della Web farm che ospita il contenuto della riunione.</span><span class="sxs-lookup"><span data-stu-id="7152c-110">For conferencing, type a URL similar to the following: **https://externalwebfarmFQDN/meet** where externalwebfarmFQDN is the external FQDN of the web farm that hosts meeting content.</span></span> <span data-ttu-id="7152c-111">Questo URL dovrebbe visualizzare la pagina di risoluzione dei problemi per le conferenze.</span><span class="sxs-lookup"><span data-stu-id="7152c-111">This URL should display the troubleshooting page for conferencing.</span></span> <span data-ttu-id="7152c-112">In alternativa, confermare che l'URL semplice per le funzioni di conferenza funzioni correttamente.</span><span class="sxs-lookup"><span data-stu-id="7152c-112">Alternatively, confirm that your Simple URL for conferencing functions correctly.</span></span> <span data-ttu-id="7152c-113">Un esempio di URL semplice per la conferenza join potrebbe essere https://meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7152c-113">An example Simple URL for the conference join might be https://meet.contoso.com</span></span>
    
      - <span data-ttu-id="7152c-114">Per l'espansione del gruppo di distribuzione, digitare un URL simile al seguente: **https://externalwebfarmFQDN/GroupExpansion/service.svc** .</span><span class="sxs-lookup"><span data-stu-id="7152c-114">For distribution group expansion, type a URL similar to the following: **https://externalwebfarmFQDN/GroupExpansion/service.svc**.</span></span> <span data-ttu-id="7152c-115">L'utente dovrebbe ricevere una richiesta di verifica HTTP, poiché la sicurezza delle directory nel servizio di espansione dei gruppi di distribuzione è configurata per l'utilizzo dell'autenticazione di Windows per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="7152c-115">The user should receive an HTTP challenge, because directory security on the distribution group expansion service is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="7152c-116">Per l'accesso esterno, digitare l'URL semplice, analogo al seguente, in **https://externalwebfarmFQDN/dialin** cui FQDNWebfarmesterna è il nome di dominio completo esterni della Web farm in cui è ospitata la pagina di chiamata in accesso esterno per le conferenze telefoniche con accesso interno.</span><span class="sxs-lookup"><span data-stu-id="7152c-116">For dial-in, type the simple URL similar to the following **https://externalwebfarmFQDN/dialin** where externalwebfarmFQDN is the external FQDN of the web farm that hosts the dial-in page for dial-in conferencing.</span></span> <span data-ttu-id="7152c-117">L'utente deve essere indirizzato alla pagina di accesso remoto.</span><span class="sxs-lookup"><span data-stu-id="7152c-117">The user should be directed to the dial-in page.</span></span> <span data-ttu-id="7152c-118">In alternativa, confermare che l'URL semplice per l'accesso remoto funzioni correttamente.</span><span class="sxs-lookup"><span data-stu-id="7152c-118">Alternatively, confirm that your Simple URL dial-in functions correctly.</span></span> <span data-ttu-id="7152c-119">Un esempio di URL semplice per l'accesso esterno può essere https://dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7152c-119">An example Simple URL for dial-in might be https://dialin.contoso.com</span></span>
    
      - <span data-ttu-id="7152c-120">Per verificare che l'URL di individuazione automatica funzioni, digitare https://lyncdiscover .</span><span class="sxs-lookup"><span data-stu-id="7152c-120">To confirm that the autodiscover URL is working, type https://lyncdiscover.</span></span> <span data-ttu-id="7152c-121">externaldomainFQDN.</span><span class="sxs-lookup"><span data-stu-id="7152c-121">externaldomainFQDN.</span></span> <span data-ttu-id="7152c-122">Il browser dovrebbe richiedere l'apertura di un file.</span><span class="sxs-lookup"><span data-stu-id="7152c-122">The browser should prompt you to open a file.</span></span> <span data-ttu-id="7152c-123">Selezionare Blocco note per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="7152c-123">Select Notepad to open it.</span></span> <span data-ttu-id="7152c-124">Una risposta tipica sarebbe simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="7152c-124">A typical response would be similar to:</span></span>
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

</div>

</div>

<span> </span>

</div>

</div>

</div>

