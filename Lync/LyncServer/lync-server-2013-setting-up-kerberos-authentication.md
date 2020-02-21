---
title: "Lync Server 2013: configurazione dell'autenticazione Kerberos"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Kerberos authentication
ms:assetid: dd8009ef-6265-4cc0-b2c7-e474cd1f4b09
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398976(v=OCS.15)
ms:contentKeyID: 48185601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42f2c781b01aaa1ac00793f97067f24233c1e8db
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200562"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="d7ba7-102">Configurazione dell'autenticazione Kerberos in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7ba7-102">Setting up Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7ba7-103">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="d7ba7-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="d7ba7-104">Lync Server 2013 supporta l'autenticazione NTLM e Kerberos per i servizi Web.</span><span class="sxs-lookup"><span data-stu-id="d7ba7-104">Lync Server 2013 supports NTLM and Kerberos authentication for Web Services.</span></span> <span data-ttu-id="d7ba7-105">Office Communications Server 2007 e Office Communications Server 2007 R2 hanno utilizzato le impostazioni predefinite di RTCComponentService e RTCService come account utente per l'esecuzione dei pool di applicazioni dei servizi Web, consentendo l'assegnazione di un nome dell'entità servizio (SPN, Service Principal Name) all'utente account e fungere da entità di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="d7ba7-105">Office Communications Server 2007 and Office Communications Server 2007 R2 used the default RTCComponentService and RTCService as the user accounts to run the Web Services application pools, allowing for a service principal name (SPN) to be assigned to the user accounts and to act as the authentication principal.</span></span> <span data-ttu-id="d7ba7-106">Lync Server utilizza NetworkService per eseguire i servizi Web e NetworkService non è in grado di assegnare nomi SPN.</span><span class="sxs-lookup"><span data-stu-id="d7ba7-106">Lync Server uses NetworkService to run Web Services and NetworkService cannot have SPNs assigned to it.</span></span>

<span data-ttu-id="d7ba7-107">Per risolvere il problema di non disporre di oggetti di Active Directory che contengano gli SPN, il pannello di controllo di Lync Server può utilizzare gli oggetti account computer per questo scopo.</span><span class="sxs-lookup"><span data-stu-id="d7ba7-107">To solve the issue of not having Active Directory objects to hold the SPNs, Lync Server Control Panel can use computer account objects for this purpose.</span></span> <span data-ttu-id="d7ba7-108">Gli oggetti account computer possono contenere i nomi SPN e non sono soggetti a scadenza della password, un problema associato all'utilizzo degli account utente nelle versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="d7ba7-108">The computer account objects can hold the SPNs and are not subject to password expiration, which was an issue with using user accounts in previous versions.</span></span>

<span data-ttu-id="d7ba7-109">È possibile utilizzare i cmdlet di Windows PowerShell per configurare gli oggetti computer per fornire l'autenticazione Kerberos.</span><span class="sxs-lookup"><span data-stu-id="d7ba7-109">You use Windows PowerShell cmdlets to configure the computer objects to provide Kerberos authentication.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d7ba7-110">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="d7ba7-110">In This Section</span></span>

  - [<span data-ttu-id="d7ba7-111">Prerequisiti per l'abilitazione dell'autenticazione Kerberos in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7ba7-111">Prerequisites for enabling Kerberos authentication in Lync Server 2013</span></span>](lync-server-2013-prerequisites-for-enabling-kerberos-authentication.md)

  - [<span data-ttu-id="d7ba7-112">Creare un account di autenticazione Kerberos in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7ba7-112">Create a Kerberos authentication account in Lync Server 2013</span></span>](lync-server-2013-create-a-kerberos-authentication-account.md)

  - [<span data-ttu-id="d7ba7-113">Assegnare un account di autenticazione Kerberos a un sito in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7ba7-113">Assign a Kerberos authentication account to a site in Lync Server 2013</span></span>](lync-server-2013-assign-a-kerberos-authentication-account-to-a-site.md)

  - [<span data-ttu-id="d7ba7-114">Configurazione delle password degli account di autenticazione Kerberos in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7ba7-114">Setting up Kerberos authentication account passwords in Lync Server 2013</span></span>](lync-server-2013-setting-up-kerberos-authentication-account-passwords.md)

  - [<span data-ttu-id="d7ba7-115">In Lync Server 2013 aggiungere l'autenticazione Kerberos ad altri siti</span><span class="sxs-lookup"><span data-stu-id="d7ba7-115">In Lync Server 2013 add Kerberos authentication to other sites</span></span>](lync-server-2013-add-kerberos-authentication-to-other-sites.md)

  - [<span data-ttu-id="d7ba7-116">In Lync Server 2013 rimuovere l'autenticazione Kerberos da un sito</span><span class="sxs-lookup"><span data-stu-id="d7ba7-116">In Lync Server 2013 remove Kerberos authentication from a site</span></span>](lync-server-2013-remove-kerberos-authentication-from-a-site.md)

  - [<span data-ttu-id="d7ba7-117">Verifica e segnalazione dello stato e dell'assegnazione dell'autenticazione Kerberos in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7ba7-117">Testing and reporting the status and assignment of Kerberos authentication in Lync Server 2013</span></span>](lync-server-2013-testing-and-reporting-the-status-and-assignment-of-kerberos-authentication.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

