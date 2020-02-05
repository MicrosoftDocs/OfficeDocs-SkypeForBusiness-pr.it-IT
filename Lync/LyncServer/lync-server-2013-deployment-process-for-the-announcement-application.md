---
title: "Lync Server 2013: processo di distribuzione per l'applicazione di annunci"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for the Announcement application
ms:assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398545(v=OCS.15)
ms:contentKeyID: 48184500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dcb56f197a32403d1207cf0a15d47e0459fc41bf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762574"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="0b6d6-102">Processo di distribuzione per l'applicazione di annuncio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b6d6-102">Deployment process for the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b6d6-103">_**Argomento Ultima modifica:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="0b6d6-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="0b6d6-104">Questa sezione fornisce una panoramica dei passaggi necessari per la distribuzione dell'applicazione di annunci.</span><span class="sxs-lookup"><span data-stu-id="0b6d6-104">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="0b6d6-105">È necessario distribuire Enterprise Voice prima di configurare gli annunci.</span><span class="sxs-lookup"><span data-stu-id="0b6d6-105">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="0b6d6-106">I componenti necessari per l'applicazione di annuncio vengono installati e abilitati quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="0b6d6-106">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="announcement-deployment-process"></a><span data-ttu-id="0b6d6-107">Processo di distribuzione degli annunci</span><span class="sxs-lookup"><span data-stu-id="0b6d6-107">Announcement Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0b6d6-108">Fase</span><span class="sxs-lookup"><span data-stu-id="0b6d6-108">Phase</span></span></th>
<th><span data-ttu-id="0b6d6-109">Passaggi</span><span class="sxs-lookup"><span data-stu-id="0b6d6-109">Steps</span></span></th>
<th><span data-ttu-id="0b6d6-110">Ruoli</span><span class="sxs-lookup"><span data-stu-id="0b6d6-110">Roles</span></span></th>
<th><span data-ttu-id="0b6d6-111">Documentazione di distribuzione</span><span class="sxs-lookup"><span data-stu-id="0b6d6-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0b6d6-112">Configurare le impostazioni degli annunci</span><span class="sxs-lookup"><span data-stu-id="0b6d6-112">Configure Announcement settings</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="0b6d6-113">Creare l'annuncio registrando e caricando i file audio o tramite sintesi vocale.</span><span class="sxs-lookup"><span data-stu-id="0b6d6-113">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span></p></li>
<li><p><span data-ttu-id="0b6d6-114">Configurare gli intervalli di numeri non assegnati nella tabella dei numeri non assegnati e associarli con l'annuncio appropriato.</span><span class="sxs-lookup"><span data-stu-id="0b6d6-114">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0b6d6-115">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="0b6d6-115">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="0b6d6-116">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="0b6d6-116">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="0b6d6-117">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="0b6d6-117">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="0b6d6-118">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="0b6d6-118">CsAdministrator</span></span></p>
<p><span data-ttu-id="0b6d6-119">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="0b6d6-119">CsViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="0b6d6-120"><a href="lync-server-2013-create-an-announcement.md">Creare un annuncio in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0b6d6-120"><a href="lync-server-2013-create-an-announcement.md">Create an announcement in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="0b6d6-121"><a href="lync-server-2013-configure-the-unassigned-number-table.md">Configurare la tabella dei numeri non assegnati in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0b6d6-121"><a href="lync-server-2013-configure-the-unassigned-number-table.md">Configure the unassigned number table in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6d6-122">Verificare la distribuzione degli annunci</span><span class="sxs-lookup"><span data-stu-id="0b6d6-122">Verify your Announcement deployment</span></span></p></td>
<td><p><span data-ttu-id="0b6d6-123">Eseguire il test ascoltando gli annunci per verificare che la configurazione funzioni come previsto.</span><span class="sxs-lookup"><span data-stu-id="0b6d6-123">Test by listening to announcements to verify that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="0b6d6-124"><a href="lync-server-2013-optional-verify-announcement-deployment.md">Opzionale Verificare la distribuzione degli annunci in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0b6d6-124"><a href="lync-server-2013-optional-verify-announcement-deployment.md">(Optional) Verify Announcement deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

