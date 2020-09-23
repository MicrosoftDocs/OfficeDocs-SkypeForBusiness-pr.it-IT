---
title: Espansione delle impostazioni dell'FQDN del server perimetrale per Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 'Per definire le proprietà in Impostazioni esterne, configurare queste opzioni:'
ms.openlocfilehash: 2de4b562d5b6a8b8ef9707d603fe5f4667893ba4
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218247"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a><span data-ttu-id="0b385-103">Espansione delle impostazioni dell'FQDN del server perimetrale per Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="0b385-103">Edge Server FQDN Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="0b385-104">Per definire le proprietà in **Impostazioni esterne**, configurare queste opzioni:</span><span class="sxs-lookup"><span data-stu-id="0b385-104">To define the properties under **External settings**, configure the following:</span></span>
  
<span data-ttu-id="0b385-105">Selezionare la casella di controllo **Abilita FQDN e indirizzo IP distinti per Web Conferencing e A/V** se si desidera definire FQDN e indirizzi IP distinti per le conferenze Web e le funzionalità audio/video.</span><span class="sxs-lookup"><span data-stu-id="0b385-105">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to define distinct Pool FQDN and IP addresses for web conferencing and audio/video.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0b385-106">Se si sceglie di non selezionare la casella di controllo per l'FQDN e gli indirizzi IP separati, è necessario fornire porte distinte per ognuno dei tre servizi forniti dal server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="0b385-106">If you choose to not select the check box for separate FQDN and IP addresses, you must provide distinct ports for each of the three services provided by the Edge Server.</span></span> <span data-ttu-id="0b385-107">L'unico nome di dominio completo che deve essere configurato è l'FQDN associato al servizio Access Edge.</span><span class="sxs-lookup"><span data-stu-id="0b385-107">The only fully qualified domain name that is to configure is the FQDN associated with the Access Edge service.</span></span> 
  
<span data-ttu-id="0b385-108">Selezionare la casella di controllo **a/v Edge è abilitato NAT** se si desidera che il servizio a/v Edge utilizzi una configurazione e un indirizzo IP NAT (Network Address Translation).</span><span class="sxs-lookup"><span data-stu-id="0b385-108">Select the **A/V Edge service is NAT enabled** check box if you want the A/V Edge service to use a network address translation (NAT) IP address and configuration.</span></span>
  
<span data-ttu-id="0b385-109">Per i servizi Edge abilitati, digitare un FQDN in **FQDN pool** e una porta in **Porte**</span><span class="sxs-lookup"><span data-stu-id="0b385-109">For the enabled Edge services, you type a **Pool FQDN** and a port under **Ports**</span></span>
  
- <span data-ttu-id="0b385-110">Definire l'FQDN del pool per **Servizio Access Edge** e una porta che identifichi in modo univoco il servizio.</span><span class="sxs-lookup"><span data-stu-id="0b385-110">Define the **Access Edge service** Pool FQDN and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="0b385-111">Definire l'FQDN del pool per **Servizio Web Conferencing Edge** (se la casella di controllo Abilita FQDN e indirizzo IP distinti per Web Conferencing e A/V è deselezionata) e una porta che identifichi in modo univoco il servizio.</span><span class="sxs-lookup"><span data-stu-id="0b385-111">Define the **Web Conferencing Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="0b385-112">Definire l'FQDN del pool per **Servizio A/V Edge** (se la casella di controllo Abilita FQDN e indirizzo IP distinti per Web Conferencing e A/V è deselezionata) e una porta che identifichi in modo univoco il servizio.</span><span class="sxs-lookup"><span data-stu-id="0b385-112">Define the **A/V Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
  <span data-ttu-id="0b385-113">**OK** Accetta le modifiche apportate nella finestra di dialogo e ne esegue il commit.</span><span class="sxs-lookup"><span data-stu-id="0b385-113">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="0b385-114">**Annulla** Rimuove le modifiche e chiude la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="0b385-114">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="0b385-115">**?** Visualizza questa schermata della Guida.</span><span class="sxs-lookup"><span data-stu-id="0b385-115">**Help** Displays this help screen.</span></span>
  

