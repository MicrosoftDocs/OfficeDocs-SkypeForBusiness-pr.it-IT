---
title: "Lync Server 2013: configurazione dell'autenticazione passiva"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server passive authentication
ms:assetid: 9a904b8d-9fce-4abf-be73-5c8e48cfb53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308569(v=OCS.15)
ms:contentKeyID: 54973690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a2e52f957a8aba7e69e97b0ec2100ffbc5a190c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756330"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-passive-authentication"></a><span data-ttu-id="e12c9-102">Configurazione dell'autenticazione passiva di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e12c9-102">Configuring Lync Server 2013 passive authentication</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e12c9-103">_**Argomento Ultima modifica:** 2013-07-11_</span><span class="sxs-lookup"><span data-stu-id="e12c9-103">_**Topic Last Modified:** 2013-07-11_</span></span>

<span data-ttu-id="e12c9-104">La sezione seguente descrive come configurare Lync Server 2013 con aggiornamenti cumulativi: luglio 2013 per supportare l'autenticazione passiva.</span><span class="sxs-lookup"><span data-stu-id="e12c9-104">The following section describes how to configure Lync Server 2013 with Cumulative Updates: July 2013 to support passive authentication.</span></span> <span data-ttu-id="e12c9-105">Una volta abilitata, agli utenti di Lync abilitati per l'autenticazione a due fattori sarà richiesto di usare una smart card fisica o virtuale e un PIN valido per accedere con Lync 2013 con gli aggiornamenti cumulativi: client di luglio 2013.</span><span class="sxs-lookup"><span data-stu-id="e12c9-105">Once enabled, Lync users who are enabled for two-factor authentication will be required to use a physical or virtual smart card and a valid PIN to sign in using the Lync 2013 with Cumulative Updates: July 2013 client.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="e12c9-106">È consigliabile che i clienti consentano l'autenticazione passiva per il registrar e i servizi Web a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="e12c9-106">It is strongly recommended that customers enable passive authentication for Registrar and Web Services at the service level.</span></span> <span data-ttu-id="e12c9-107">Se l'autenticazione passiva è abilitata per i servizi di registrazione e Web a livello globale, probabilmente si verificheranno errori di autenticazione a livello di organizzazione per gli utenti che non accedono con Lync 2013 con gli aggiornamenti cumulativi: client desktop client di luglio 2013.</span><span class="sxs-lookup"><span data-stu-id="e12c9-107">If passive authentication is enabled for Registrar and Web Services at the global level, it will likely result in organization-wide authentication failures for users who are not signing in with the Lync 2013 with Cumulative Updates: July 2013 client desktop client.</span></span>



</div>

<div>

## <a name="web-service-configuration"></a><span data-ttu-id="e12c9-108">Configurazione del servizio Web</span><span class="sxs-lookup"><span data-stu-id="e12c9-108">Web Service Configuration</span></span>

<span data-ttu-id="e12c9-109">I passaggi seguenti descrivono come creare una configurazione di servizio Web personalizzata per direttori, pool Enterprise e server Standard Edition che verranno abilitati per l'autenticazione passiva.</span><span class="sxs-lookup"><span data-stu-id="e12c9-109">The following steps describe how to create a custom web service configuration for Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

<span data-ttu-id="e12c9-110">**Per creare una configurazione di un servizio Web personalizzato**</span><span class="sxs-lookup"><span data-stu-id="e12c9-110">**To create a custom web service configuration**</span></span>

1.  <span data-ttu-id="e12c9-111">Accedere a Lync Server 2013 con gli aggiornamenti cumulativi: luglio 2013 front end server con un account di amministratore di Lync.</span><span class="sxs-lookup"><span data-stu-id="e12c9-111">Log in to your Lync Server 2013 with Cumulative Updates: July 2013 Front End server using a Lync administrator account.</span></span>

2.  <span data-ttu-id="e12c9-112">Avviare Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e12c9-112">Launch the Lync Server 2013 Management Shell.</span></span>

3.  <span data-ttu-id="e12c9-113">Dalla riga di comando di Lync Server Management Shell creare una nuova configurazione del servizio Web per ogni Director, pool Enterprise e server Standard Edition che verrà abilitato per l'autenticazione passiva eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e12c9-113">From the Lync Server Management Shell command-line, create a new Web Service configuration for each Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command:</span></span>
    ```powershell
    New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    ```

    <div class="">
    

    > [!WARNING]  
    > <span data-ttu-id="e12c9-114">Il valore per l'FQDN di WsFedPassiveMetadataUri è il nome del servizio federativo del server ADFS 2,0.</span><span class="sxs-lookup"><span data-stu-id="e12c9-114">The value for the WsFedPassiveMetadataUri FQDN is the Federation Service Name of your AD FS 2.0 server.</span></span> <span data-ttu-id="e12c9-115">Il valore nome servizio federativo può essere trovato nella console di gestione di ADFS 2,0 facendo clic con il pulsante destro del mouse su <STRONG>servizio</STRONG> dal riquadro di spostamento e quindi selezionando <STRONG>modifica proprietà servizio federativo</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="e12c9-115">The Federation Service Name value can be found in the AD FS 2.0 Management Console by right-clicking on <STRONG>Service</STRONG> from the navigation pane and then selecting <STRONG>Edit Federation Service Properties</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="e12c9-116">Verificare che i valori UseWsFedPassiveAuth e WsFedPassiveMetadataUri siano stati impostati correttamente eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e12c9-116">Verify that the UseWsFedPassiveAuth and WsFedPassiveMetadataUri values were set correctly by running the following command:</span></span>
     ```powershell
     Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
     ```
5.  <span data-ttu-id="e12c9-117">Per i client, l'autenticazione passiva è il metodo di autenticazione meno preferibile per l'autenticazione webticket.</span><span class="sxs-lookup"><span data-stu-id="e12c9-117">For clients, Passive Authentication is the least preferred authentication method for webticket authentication.</span></span> <span data-ttu-id="e12c9-118">Per tutti i direttori, i pool Enterprise e i server Standard Edition che verranno abilitati per l'autenticazione passiva, tutti gli altri tipi di autenticazione devono essere disabilitati in servizi Web Lync eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e12c9-118">For all Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication, all other authentication types must be disabled in Lync Web Services by running the following command:</span></span>
    ```powershell
    Set-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
     ```
6.  <span data-ttu-id="e12c9-119">Verificare che tutti gli altri tipi di autenticazione siano stati correttamente disabilitati eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e12c9-119">Verify that all other authentication types have been successfully disabled by running the following command:</span></span>
    ```powershell
    Get-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
     ```
</div>

<div>

## <a name="proxy-configuration"></a><span data-ttu-id="e12c9-120">Configurazione proxy</span><span class="sxs-lookup"><span data-stu-id="e12c9-120">Proxy Configuration</span></span>

<span data-ttu-id="e12c9-121">Quando l'autenticazione dei certificati è disabilitata per i servizi Web Lync, il client Lync utilizzerà un tipo di autenticazione meno consigliato, ad esempio Kerberos o NTLM, per eseguire l'autenticazione nel servizio registrar.</span><span class="sxs-lookup"><span data-stu-id="e12c9-121">When certificate authentication is disabled for Lync Web Services, the Lync client will use a less preferred authentication type, such as Kerberos or NTLM, to authenticate to the Registrar service.</span></span> <span data-ttu-id="e12c9-122">L'autenticazione del certificato è ancora necessaria per consentire al client Lync di recuperare un ticket, ma Kerberos e NTLM devono essere disabilitati per il servizio registrar.</span><span class="sxs-lookup"><span data-stu-id="e12c9-122">Certificate authentication is still needed to allow the Lync client to retrieve a webticket, however, Kerberos and NTLM must be disabled for the Registrar service.</span></span>

<span data-ttu-id="e12c9-123">I passaggi seguenti descrivono come creare una configurazione proxy personalizzata per i pool di Edge, i pool Enterprise e i server Standard Edition che verranno abilitati per l'autenticazione passiva.</span><span class="sxs-lookup"><span data-stu-id="e12c9-123">The following steps describe how to create a custom proxy configuration for Edge Pools, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

<span data-ttu-id="e12c9-124">**Per creare una configurazione proxy personalizzata**</span><span class="sxs-lookup"><span data-stu-id="e12c9-124">**To create a custom proxy configuration**</span></span>

1.  <span data-ttu-id="e12c9-125">Dalla riga di comando di Lync Server Management Shell creare una nuova configurazione proxy per ogni Lync Server 2013 con aggiornamenti cumulativi: luglio 2013 Edge pool, pool Enterprise e server Standard Edition che verranno abilitati per l'autenticazione passiva eseguendo il comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e12c9-125">From the Lync Server Management Shell command-line, create a new proxy configuration for each Lync Server 2013 with Cumulative Updates: July 2013 Edge Pool, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following commands:</span></span>
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```

2.  <span data-ttu-id="e12c9-126">Verificare che tutti gli altri tipi di autenticazione proxy siano stati correttamente disabilitati eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e12c9-126">Verify that all other proxy authentication types have been successfully disabled by running the following command:</span></span>
    ```powershell
    Get-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com"
         | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
     ```
</div>

</div>

<span> </span>

</div>

</div>

</div>

