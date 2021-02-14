---
title: Espansione delle impostazioni del computer perimetrale per Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: "Per modificare le proprietà dei computer server perimetrali come singolo server perimetrale o come computer membri in un pool di server perimetrali, configurare le impostazioni di configurazione del nome server e dell'indirizzo IP:"
ms.openlocfilehash: e25f68ec510cf15cd58872a8c584dc71aa939f48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807136"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a><span data-ttu-id="ced85-103">Espansione delle impostazioni del computer perimetrale per Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="ced85-103">Edge Machine Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="ced85-104">Per modificare le proprietà dei computer server perimetrali come singolo server perimetrale o come computer membri in un pool di server perimetrali, configurare le impostazioni di configurazione del nome server e **dell'indirizzo IP:**</span><span class="sxs-lookup"><span data-stu-id="ced85-104">To edit the properties for Edge Server computers as an single Edge Server or as member computers in an Edge pool, you configure **Server name and IP address configuration** settings:</span></span>
  
- <span data-ttu-id="ced85-105">**Nome interno o FQDN:** digitare il nome del computer a cui si fa riferimento nel DNS (Domain Name System).</span><span class="sxs-lookup"><span data-stu-id="ced85-105">**Internal name or FQDN**: Type the name of the computer as it is referenced in the domain name system (DNS).</span></span> 
    
- <span data-ttu-id="ced85-106">**Indirizzo IPv4 interno:** digitare l'indirizzo IPv4 della scheda nic (Network Interface Card) interna del computer.</span><span class="sxs-lookup"><span data-stu-id="ced85-106">**Internal IPv4 address**: Type the IPv4 address of the internal network interface card (NIC) for this computer.</span></span>
    
- <span data-ttu-id="ced85-107">Configurare l'indirizzo **IPv4 esterno** del servizio **Access Edge** associato al computer</span><span class="sxs-lookup"><span data-stu-id="ced85-107">You configure the **Access Edge service** **External IPv4 address** associated with this computer</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ced85-108">Se si è scelto di utilizzare un singolo indirizzo IP per la configurazione del server perimetrale, sarà possibile modificare solo l'indirizzo IPv4 esterno per il servizio Access Edge.</span><span class="sxs-lookup"><span data-stu-id="ced85-108">If you selected to use a single IP address for the Edge Server configuration, you will only be able to edit the external IPv4 address for the Access Edge service.</span></span> <span data-ttu-id="ced85-109">Gli altri servizi Edge condivideranno lo stesso indirizzo IPv4 del servizio Access Edge.</span><span class="sxs-lookup"><span data-stu-id="ced85-109">The other Edge services will share the same IPv4 address as the Access Edge service.</span></span> 
  
- <span data-ttu-id="ced85-110">Se disponibile per la modifica, configurare l'indirizzo **IPv4** esterno del servizio **Web Conferencing** associato al computer</span><span class="sxs-lookup"><span data-stu-id="ced85-110">If available to edit, you configure the **Web Conferencing service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="ced85-111">Se disponibile per la modifica, configurare l'indirizzo **IPv4** esterno del servizio **A/V Edge** associato al computer</span><span class="sxs-lookup"><span data-stu-id="ced85-111">If available to edit, you configure the **A/V Edge service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="ced85-112">Se disponibile per la modifica, configurare l'indirizzo **IPv4** pubblico abilitato per NAT associato al computer.</span><span class="sxs-lookup"><span data-stu-id="ced85-112">If available to edit, you configure the **NAT-enabled public IPv4 address** associated with this computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ced85-113">La proprietà di configurazione per l'indirizzo **IPv4** pubblico abilitato per NAT sarà disponibile per la modifica solo se si è scelto di fornire nat (Network Address Translation) per il servizio A/V Edge</span><span class="sxs-lookup"><span data-stu-id="ced85-113">The configuration property for **NAT-enabled public IPv4 address** will only be available to edit if you chose to provide network address translation (NAT) for the A/V Edge service</span></span>
  
  <span data-ttu-id="ced85-114">**OK** Accetta le modifiche apportate nella finestra di dialogo e ne esegue il commit.</span><span class="sxs-lookup"><span data-stu-id="ced85-114">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="ced85-115">**Annulla** Rimuove le modifiche e chiude la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="ced85-115">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="ced85-116">**?** Visualizza questa schermata della Guida.</span><span class="sxs-lookup"><span data-stu-id="ced85-116">**Help** Displays this help screen.</span></span>
  

