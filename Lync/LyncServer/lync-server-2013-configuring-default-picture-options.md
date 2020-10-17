---
title: 'Lync Server 2013: configurazione delle opzioni predefinite per le immagini'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring default picture options
ms:assetid: b1c986f0-6400-447a-9e36-78c1c3a4f793
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn205074(v=OCS.15)
ms:contentKeyID: 56280893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc6bb0368b97e41402f2e0abf0834cf23f078c08
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514813"
---
# <a name="configuring-default-picture-options-in-lync-server-2013"></a><span data-ttu-id="003ba-102">Configurazione delle opzioni predefinite per le immagini in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="003ba-102">Configuring default picture options in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="003ba-103">_**Ultimo argomento modificato:** 2013-03-22_</span><span class="sxs-lookup"><span data-stu-id="003ba-103">_**Topic Last Modified:** 2013-03-22_</span></span>

<span data-ttu-id="003ba-104">Per impostazione predefinita, le immagini degli utenti vengono visualizzate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="003ba-104">By default, users’ pictures are automatically displayed.</span></span> <span data-ttu-id="003ba-105">Se gli utenti desiderano nascondere le proprie immagini, è possibile selezionare l'opzione **Nascondi immagine** nel client Lync.</span><span class="sxs-lookup"><span data-stu-id="003ba-105">If users want to hide their pictures, they can select the **Hide my picture** option in the Lync client.</span></span> <span data-ttu-id="003ba-106">Tuttavia, questa impostazione viene ignorata da altre applicazioni di Office.</span><span class="sxs-lookup"><span data-stu-id="003ba-106">However, this setting is ignored by some other Office applications.</span></span>

<span data-ttu-id="003ba-107">Se la possibilità di visualizzare immagini anche quando è disattivata dall'utente è un problema, è possibile modificare le impostazioni di visualizzazione delle immagini di Lync globalmente o per un sito o un servizio in modo che le immagini degli utenti non vengano visualizzate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="003ba-107">If the possibility of displaying pictures even when turned off by the user is a concern, you can change Lync picture display settings globally or for a site or service so that users’ pictures are not shown by default.</span></span> <span data-ttu-id="003ba-108">Utilizzare il seguente cmdlet di Lync Server Management Shell in modo che le immagini dell'utente non vengano visualizzate, a meno che non vengano esplicitamente selezionate l'opzione **Mostra immagine personale** nel client:</span><span class="sxs-lookup"><span data-stu-id="003ba-108">Use the following Lync Server Management Shell cmdlet so that user’s pictures will not be shown unless they explicitly select the **Show my picture** option in the client:</span></span>

    Set-CsPrivacyConfiguration -DisplayPublishedPhotoDefault $False

<span data-ttu-id="003ba-109">Per ulteriori informazioni su questo cmdlet, vedere [Set-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration) nella documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="003ba-109">For more information about this cmdlet, see the [Set-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration) in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

