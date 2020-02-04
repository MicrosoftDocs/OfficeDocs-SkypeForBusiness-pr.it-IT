---
title: "Lync Server 2013: Verificare l'accesso tramite il proxy inverso"
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
ms.openlocfilehash: e13f7e23f3404191f7251c1f49bda6f8935a2929
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-access-through-your-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="652da-102">Verificare l'accesso tramite il proxy inverso in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="652da-102">Verify access through your reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="652da-103">_**Argomento Ultima modifica:** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="652da-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="652da-104">Usare la procedura seguente per verificare che gli utenti possano accedere alle informazioni sul proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="652da-104">Use the following procedure to verify that your users can access information on the reverse proxy.</span></span> <span data-ttu-id="652da-105">Può essere necessario completare la configurazione del firewall e la configurazione DNS (Domain Name System) prima che Access funzioni correttamente.</span><span class="sxs-lookup"><span data-stu-id="652da-105">You might need to complete the firewall configuration and Domain Name System (DNS) configuration before access will work correctly.</span></span>

<div>

## <a name="to-verify-that-you-can-access-the-website-through-the-internet"></a><span data-ttu-id="652da-106">Per verificare che sia possibile accedere al sito Web tramite Internet</span><span class="sxs-lookup"><span data-stu-id="652da-106">To verify that you can access the website through the Internet</span></span>

  - <span data-ttu-id="652da-107">Aprire un Web browser, digitare gli URL nella barra degli **indirizzi** che i client usano per accedere ai file della Rubrica e al sito Web per i servizi di conferenza come segue:</span><span class="sxs-lookup"><span data-stu-id="652da-107">Open a web browser, type the URLs in the **Address** bar that clients use to access the Address Book files and the website for conferencing as follows:</span></span>
    
      - <span data-ttu-id="652da-108">Per server rubrica, digitare un URL simile al seguente: **https://externalwebfarmFQDN/abs** dove FQDNWebfarmesterna è il nome di dominio completo esterno dei servizi Web esterni che ospitano i servizi Rubrica.</span><span class="sxs-lookup"><span data-stu-id="652da-108">For Address Book Server, type a URL similar to the following: **https://externalwebfarmFQDN/abs** where externalwebfarmFQDN is the external FQDN of the external web services that hosts Address Book services.</span></span> <span data-ttu-id="652da-109">L'utente dovrebbe ricevere una sfida HTTP, perché la sicurezza della directory nella cartella del server rubrica è configurata per impostazione predefinita in autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="652da-109">The user should receive an HTTP challenge, because directory security on the Address Book Server folder is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="652da-110">Per i servizi di conferenza, digitare un URL simile al **https://externalwebfarmFQDN/meet** seguente: dove FQDNWebfarmesterna è il nome di dominio completo esterno della Web farm che ospita il contenuto della riunione.</span><span class="sxs-lookup"><span data-stu-id="652da-110">For conferencing, type a URL similar to the following: **https://externalwebfarmFQDN/meet** where externalwebfarmFQDN is the external FQDN of the web farm that hosts meeting content.</span></span> <span data-ttu-id="652da-111">Questo URL dovrebbe visualizzare la pagina di risoluzione dei problemi per i servizi di conferenza.</span><span class="sxs-lookup"><span data-stu-id="652da-111">This URL should display the troubleshooting page for conferencing.</span></span> <span data-ttu-id="652da-112">In alternativa, verificare che l'URL semplice per le funzioni di conferenza sia corretto.</span><span class="sxs-lookup"><span data-stu-id="652da-112">Alternatively, confirm that your Simple URL for conferencing functions correctly.</span></span> <span data-ttu-id="652da-113">Un esempio di URL semplice per il join di conferenza potrebbe esserehttps://meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="652da-113">An example Simple URL for the conference join might be https://meet.contoso.com</span></span>
    
      - <span data-ttu-id="652da-114">Per l'espansione del gruppo di distribuzione, digitare un URL simile al **https://externalwebfarmFQDN/GroupExpansion/service.svc**seguente:.</span><span class="sxs-lookup"><span data-stu-id="652da-114">For distribution group expansion, type a URL similar to the following: **https://externalwebfarmFQDN/GroupExpansion/service.svc**.</span></span> <span data-ttu-id="652da-115">L'utente dovrebbe ricevere una sfida HTTP, perché la sicurezza della directory nel servizio di espansione del gruppo di distribuzione è configurata per impostazione predefinita per l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="652da-115">The user should receive an HTTP challenge, because directory security on the distribution group expansion service is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="652da-116">Per l'accesso esterno, digitare l'URL semplice in modo simile al **https://externalwebfarmFQDN/dialin** seguente, dove FQDNWebfarmesterna è il nome di dominio completo esterni della Web farm che ospita la pagina per la telefonia esterna con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="652da-116">For dial-in, type the simple URL similar to the following **https://externalwebfarmFQDN/dialin** where externalwebfarmFQDN is the external FQDN of the web farm that hosts the dial-in page for dial-in conferencing.</span></span> <span data-ttu-id="652da-117">L'utente deve essere indirizzato alla pagina di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="652da-117">The user should be directed to the dial-in page.</span></span> <span data-ttu-id="652da-118">In alternativa, verificare che le funzioni di accesso semplice per gli URL siano corrette.</span><span class="sxs-lookup"><span data-stu-id="652da-118">Alternatively, confirm that your Simple URL dial-in functions correctly.</span></span> <span data-ttu-id="652da-119">Un esempio di URL semplice per l'accesso esterno potrebbe esserehttps://dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="652da-119">An example Simple URL for dial-in might be https://dialin.contoso.com</span></span>
    
      - <span data-ttu-id="652da-120">Per verificare che l'URL di individuazione automatica funzioni, digitare https://lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="652da-120">To confirm that the autodiscover URL is working, type https://lyncdiscover.</span></span> <span data-ttu-id="652da-121">externaldomainFQDN.</span><span class="sxs-lookup"><span data-stu-id="652da-121">externaldomainFQDN.</span></span> <span data-ttu-id="652da-122">Il browser dovrebbe richiedere l'apertura di un file.</span><span class="sxs-lookup"><span data-stu-id="652da-122">The browser should prompt you to open a file.</span></span> <span data-ttu-id="652da-123">Selezionare Blocco note per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="652da-123">Select Notepad to open it.</span></span> <span data-ttu-id="652da-124">Una risposta tipica sarebbe simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="652da-124">A typical response would be similar to:</span></span>
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

</div>

</div>

<span> </span>

</div>

</div>

</div>

