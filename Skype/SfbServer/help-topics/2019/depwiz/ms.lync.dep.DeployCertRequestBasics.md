---
title: Richiesta di certificato (Basic)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployCertRequestBasics
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2c6b40d5-207a-4ca9-a090-e43350f4968f
ROBOTS: NOINDEX, NOFOLLOW
description: Nella pagina Impostazioni nome e sicurezza viene visualizzata una casella di testo per definire un nome descrittivo, un elenco a discesa per la lunghezza in bit della coppia di chiavi privata e pubblica e una casella di controllo che consente di contrassegnare la chiave privata del certificato come esportabile.
ms.openlocfilehash: f1945089d8f58297476c98228fa2cff68e88c24f
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41705711"
---
# <a name="certificate-request-basic"></a><span data-ttu-id="48c69-103">Richiesta di certificato (Basic)</span><span class="sxs-lookup"><span data-stu-id="48c69-103">Certificate Request (Basic)</span></span>
 
<span data-ttu-id="48c69-104">Nella pagina **Impostazioni nome e sicurezza** viene visualizzata una casella di testo per definire un **nome descrittivo**, un elenco a discesa per la **lunghezza in bit** della coppia di chiavi privata e pubblica e una casella di controllo che consente di **contrassegnare la chiave privata del certificato come esportabile**.</span><span class="sxs-lookup"><span data-stu-id="48c69-104">The **Name and Security Settings** page provides a text box to define a **Friendly Name**, a drop-down list for the **Bit length** of the private and public key pair, and a check box that enables you to **Mark the certificate's private key as exportable**.</span></span>
  
<span data-ttu-id="48c69-105">Il nome descrittivo di un certificato rappresenta un nome facilmente riconoscibile che consente alla persona che visualizza il certificato di identificarlo più facilmente.</span><span class="sxs-lookup"><span data-stu-id="48c69-105">The friendly, or simple, name on a certificate is an easily recognizable name that makes it easier for the person who views the certificate to identify it.</span></span>
  
<span data-ttu-id="48c69-106">La lunghezza in bit della coppia chiave privata e chiave pubblica può essere impostata su 1024, 2048 o 4096.</span><span class="sxs-lookup"><span data-stu-id="48c69-106">The Bit length of the private and public key pair can be selected as 1024, 2048, or 4096.</span></span>
  
<span data-ttu-id="48c69-107">Selezionando la casella di controllo per **contrassegnare la chiave privata del certificato come esportabile, è** possibile esportare e spostare il certificato e la chiave privata in un altro computer o server.</span><span class="sxs-lookup"><span data-stu-id="48c69-107">Selecting the check box for **Mark the certificate's private key as exportable** allows the certificate and private key to be exported and moved to another computer or server.</span></span> <span data-ttu-id="48c69-108">L'unico caso in cui è necessaria tale operazione è durante la creazione di un pool di server perimetrali per il servizio MRAS (Media Relay Authentication Service).</span><span class="sxs-lookup"><span data-stu-id="48c69-108">The only time that this is required is when you are creating a pool of Edge Servers for the media relay authentication service (MRAS).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="48c69-109">Per mantenere la sicurezza del certificato e della coppia di chiavi, è necessario selezionare l'opzione contrassegna la chiave privata del certificato come esportabile solo se è assolutamente necessario.</span><span class="sxs-lookup"><span data-stu-id="48c69-109">To help maintain the security of the certificate and the key pair, you should select the Mark the certificate's private key as exportable option only if it is absolutely necessary.</span></span> 
  

