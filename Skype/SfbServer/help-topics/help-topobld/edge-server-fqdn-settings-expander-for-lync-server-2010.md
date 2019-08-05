---
title: Expander (FQDN) delle impostazioni di Edge Server per Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 'Per definire le proprietà in impostazioni esterne, configurare le operazioni seguenti:'
ms.openlocfilehash: 6b833e89a8e1288af9a203dd5f44201c253ff2f9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189551"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a><span data-ttu-id="c7893-103">Expander (FQDN) delle impostazioni di Edge Server per Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="c7893-103">Edge Server FQDN Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="c7893-104">Per definire le proprietà in **impostazioni esterne**, configurare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c7893-104">To define the properties under **External settings**, configure the following:</span></span>
  
<span data-ttu-id="c7893-105">Selezionare la casella di controllo **attiva FQDN separato e indirizzo IP per le conferenze Web e a/V** se si vuole definire il nome di dominio completo del pool e gli indirizzi IP per le conferenze Web e l'audio/video.</span><span class="sxs-lookup"><span data-stu-id="c7893-105">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to define distinct Pool FQDN and IP addresses for web conferencing and audio/video.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c7893-106">Se si sceglie di non selezionare la casella di controllo per nomi di dominio completi e indirizzi IP separati, è necessario fornire porte distinte per ognuno dei tre servizi forniti dall'Edge Server.</span><span class="sxs-lookup"><span data-stu-id="c7893-106">If you choose to not select the check box for separate FQDN and IP addresses, you must provide distinct ports for each of the three services provided by the Edge Server.</span></span> <span data-ttu-id="c7893-107">L'unico nome di dominio completo che deve essere configurato è l'FQDN associato al servizio Access Edge.</span><span class="sxs-lookup"><span data-stu-id="c7893-107">The only fully qualified domain name that is to configure is the FQDN associated with the Access Edge service.</span></span> 
  
<span data-ttu-id="c7893-108">Selezionare la casella di controllo **a/v Edge è abilitata per NAT** se si vuole che l'a/v Edge service usi un indirizzo IP e la configurazione NAT (Network Address Translation).</span><span class="sxs-lookup"><span data-stu-id="c7893-108">Select the **A/V Edge service is NAT enabled** check box if you want the A/V Edge service to use a network address translation (NAT) IP address and configuration.</span></span>
  
<span data-ttu-id="c7893-109">Per i servizi Edge abilitati, è possibile digitare un **nome di dominio completo del pool** e una porta in **porte**</span><span class="sxs-lookup"><span data-stu-id="c7893-109">For the enabled Edge services, you type a **Pool FQDN** and a port under **Ports**</span></span>
  
- <span data-ttu-id="c7893-110">Definisci il nome di dominio completo del pool di **servizi Access Edge** e una porta che identifica in modo univoco il servizio.</span><span class="sxs-lookup"><span data-stu-id="c7893-110">Define the **Access Edge service** Pool FQDN and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="c7893-111">Definire il nome di dominio completo del pool di **servizi Web Conferencing Edge** (se è selezionata l'opzione Abilita FQDN separato e indirizzo IP per le conferenze Web e a/V non è selezionato) e una porta che identifica in modo univoco il servizio.</span><span class="sxs-lookup"><span data-stu-id="c7893-111">Define the **Web Conferencing Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="c7893-112">Definire il nome di dominio completo del pool **di servizi a/v Edge** (se è selezionata l'opzione Abilita FQDN separato e indirizzo IP per le conferenze Web e a/v) e una porta che identifica in modo univoco il servizio.</span><span class="sxs-lookup"><span data-stu-id="c7893-112">Define the **A/V Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
  <span data-ttu-id="c7893-113">**OK** Consente di accettare e salvare le modifiche nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="c7893-113">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="c7893-114">**Annulla** Consente di eliminare le modifiche e di chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="c7893-114">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="c7893-115">**Guida** Consente di visualizzare questa schermata della Guida.</span><span class="sxs-lookup"><span data-stu-id="c7893-115">**Help** Displays this help screen.</span></span>
  

