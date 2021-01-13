---
title: Espansione delle impostazioni del servizio Mediation per Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 230e0a08-9e16-4bbd-b550-1f04bad8ddbc
description: 'Per modificare le proprietà del servizio Mediation, definire le proprietà seguenti:'
ms.openlocfilehash: ddc6ab56f848179800b6398b7a638cdb7a061a9f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806686"
---
# <a name="mediation-service-settings-expander-for-lync-server-2010"></a><span data-ttu-id="0e912-103">Espansione delle impostazioni del servizio Mediation per Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="0e912-103">Mediation Service Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="0e912-104">Per modificare le proprietà del servizio Mediation, definire le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="0e912-104">You edit the properties of the Mediation service by defining the following properties:</span></span>
  
- <span data-ttu-id="0e912-p101">**Porte di attesa**: definire la porta **TLS** di attesa per il servizio Mediation. Per impostazione predefinita, il valore della porta è TCP 5067 su TLS (Transport Layer Security)</span><span class="sxs-lookup"><span data-stu-id="0e912-p101">**Listening ports**: Define the **TLS** port that the Mediation service will listen on. By default, the port value is TCP 5067 over transport layer security (TLS)</span></span>
    
    <span data-ttu-id="0e912-p102">Se lo si desidera, definire un valore di porta **TCP**. Per impostazione predefinita, il valore è TCP 5068.</span><span class="sxs-lookup"><span data-stu-id="0e912-p102">Optionally, you define a **TCP** port value. By default, the value is TCP 5068.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0e912-p103">Per abilitare l'impostazione del valore della porta TCP, selezionare **Abilita la porta TCP**. Per informazioni sui requisiti relativi alle impostazioni di porta necessarie per comunicare con il servizio Mediation, fare riferimento alla documentazione per il gateway PSTN (Public Switched Telephone Network) o IP-PBX (Internet Protocol Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="0e912-p103">The TCP port value setting is enabled by selecting **Enable TCP port**. You should refer to the documentation for your Public Switched Telephone Network (PSTN) Gateway or Internet Protocol Private Branch Exchange (IP-PBX) for the requirements for the port settings required to communicate with the Mediation service.</span></span> 
  
- <span data-ttu-id="0e912-111">Selezionare **Abilita la porta TCP** per definire il valore di porta per le comunicazioni TCP dal gateway PSTN o IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="0e912-111">You **Enable TCP port** to define the port value for TCP communications from your PSTN gateway or IP-PBX.</span></span>
    
- <span data-ttu-id="0e912-112">Un elenco di **Trunk** (ovvero trunk SIP, Session Initiation Protocol), **Gateway** (gateway PSTN o IP-PBX) e **Sito** (sito configurato per il trunk e il gateway) attualmente associati ed esistenti.</span><span class="sxs-lookup"><span data-stu-id="0e912-112">A listing of currently associated and existing **Trunk** (that is, Session Initiation Protocol (SIP) Trunks), **Gateway** (PSTN gateway or IP-PBX) and **Site** (configured site for the trunk and gateway).</span></span>
    
- <span data-ttu-id="0e912-p104">Selezionare un trunk, un gateway e un sito e fare clic su **Rendi predefinito** per impostare la selezione come predefinita per il Mediation Server. Selezionare l'impostazione predefinita corrente e fare clic su **Annulla predefinito** per rimuovere la selezione come impostazione predefinita corrente. Selezionare quindi una nuova impostazione predefinita e fare clic su **Rendi predefinito**.</span><span class="sxs-lookup"><span data-stu-id="0e912-p104">You select a Trunk, Gateway and Site and click **Make Default** to set the selection as the default for this Mediation service. You select the current default and click **Unmake Default** to remove the selection as the current default. You then select a new default and click **Make Default**.</span></span>
    
  <span data-ttu-id="0e912-116">**OK** Accetta le modifiche apportate nella finestra di dialogo e ne esegue il commit.</span><span class="sxs-lookup"><span data-stu-id="0e912-116">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="0e912-117">**Annulla** Rimuove le modifiche e chiude la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="0e912-117">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="0e912-118">**?** Visualizza questa schermata della Guida.</span><span class="sxs-lookup"><span data-stu-id="0e912-118">**Help** Displays this help screen.</span></span>
  

