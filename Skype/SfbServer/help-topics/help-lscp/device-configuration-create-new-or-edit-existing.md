---
title: Configurazione dispositivo Crea nuovo o Modifica esistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
description: Nella pagina Nuova configurazione dispositivo o Modifica configurazione dispositivo è possibile creare o modificare una raccolta di impostazioni utilizzate per gestire Skype for Business Phone Edition. Tali impostazioni consentono di configurare aspetti quali la modalità di sicurezza richiesta, il livello di registrazione del dispositivo, le impostazioni Qualità vocale servizio (QoS) e se bloccare automaticamente o meno i telefoni dopo uno specifico periodo di inattività.
ms.openlocfilehash: b0973c73580aee3cfc81dfb79ac65613ddfcf204
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119925"
---
# <a name="device-configuration-create-new-or-edit-existing"></a><span data-ttu-id="d9c0e-104">Configurazione dispositivo: crearne una nuova o modificarne una esistente</span><span class="sxs-lookup"><span data-stu-id="d9c0e-104">Device Configuration: Create New or Edit Existing</span></span>
 
<span data-ttu-id="d9c0e-105">Nella pagina **Nuova configurazione dispositivo** o Modifica configurazione dispositivo è possibile creare o modificare una raccolta di impostazioni utilizzate per gestire Skype for Business Phone Edition. </span><span class="sxs-lookup"><span data-stu-id="d9c0e-105">On the **New Device Configuration** or **Edit Device Configuration** page, you can create or modify a collection of settings used to manage Skype for Business Phone Edition.</span></span> <span data-ttu-id="d9c0e-106">Tali impostazioni consentono di configurare aspetti quali la modalità di sicurezza richiesta, il livello di registrazione del dispositivo, le impostazioni Qualità vocale servizio (QoS) e se bloccare automaticamente o meno i telefoni dopo uno specifico periodo di inattività.</span><span class="sxs-lookup"><span data-stu-id="d9c0e-106">These settings enable you to configure such things as the required security mode, device logging level, Voice Quality of Service (QoS) settings, and whether or not phones should automatically lock after a specified period of inactivity.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="d9c0e-107">Attività eseguibili</span><span class="sxs-lookup"><span data-stu-id="d9c0e-107">Tasks you can perform</span></span>

<span data-ttu-id="d9c0e-108">Nella pagina **Nuova configurazione dispositivo** o **Modifica configurazione dispositivo** è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="d9c0e-108">You can perform the following tasks on the **New Device Configuration** or **Edit Device Configuration** page:</span></span>
  
- <span data-ttu-id="d9c0e-109">Aggiungere una nuova configurazione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d9c0e-109">Add a new device configuration.</span></span>
    
- <span data-ttu-id="d9c0e-110">Modificare le proprietà di una configurazione del dispositivo esistente.</span><span class="sxs-lookup"><span data-stu-id="d9c0e-110">Modify the properties of an existing device configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="d9c0e-111">Riferimento all'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="d9c0e-111">UI Reference</span></span>

<span data-ttu-id="d9c0e-112">Negli elenchi seguenti sono descritti i menu, i comandi, i campi e le proprietà della pagina.</span><span class="sxs-lookup"><span data-stu-id="d9c0e-112">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="d9c0e-113">**Ambito** Identifica l'ambito (globale o sito) della configurazione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d9c0e-113">**Scope** Identifies the scope (Global or Site) of the device configuration.</span></span>
    
- <span data-ttu-id="d9c0e-114">**Nome** Puoi aggiungere o modificare il nome della configurazione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d9c0e-114">**Name** You can add or modify the name of the device configuration.</span></span>
    
- <span data-ttu-id="d9c0e-115">**Sicurezza SIP** È possibile configurare i requisiti di trasporto e autenticazione per i dispositivi Skype for Business Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="d9c0e-115">**SIP security** You can configure transport and authentication requirements for Skype for Business Phone Edition devices.</span></span> <span data-ttu-id="d9c0e-116">È possibile scegliere tra le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d9c0e-116">You can select from the following options:</span></span>
    
  - <span data-ttu-id="d9c0e-117">**Bassa** Consentire qualsiasi tipo di autorizzazione o trasporto.</span><span class="sxs-lookup"><span data-stu-id="d9c0e-117">**Low** Allow any type of authorization or transport.</span></span>
    
  - <span data-ttu-id="d9c0e-118">**Medio** Per l'autenticazione utente è necessario NTLM o Kerberos.</span><span class="sxs-lookup"><span data-stu-id="d9c0e-118">**Medium** NTLM or Kerberos is required for user authentication.</span></span>
    
  - <span data-ttu-id="d9c0e-119">**High** NtLM o Kerberos è necessario per l'autenticazione utente e TLS è necessario per le connessioni SIP.</span><span class="sxs-lookup"><span data-stu-id="d9c0e-119">**High** NTLM or Kerberos is required for user authentication and TLS is required for SIP connections.</span></span>
    
- <span data-ttu-id="d9c0e-120">**Livello di registrazione** È possibile abilitare la registrazione nel dispositivo per le comunicazioni unificate.</span><span class="sxs-lookup"><span data-stu-id="d9c0e-120">**Logging level** You can enable logging on the UC device.</span></span> <span data-ttu-id="d9c0e-121">I valori validi sono Disattivato, Basso, Medio e Alto.</span><span class="sxs-lookup"><span data-stu-id="d9c0e-121">Valid values are: Off; Low; Medium; and High.</span></span> <span data-ttu-id="d9c0e-122">Il valore predefinito è Disattivato.</span><span class="sxs-lookup"><span data-stu-id="d9c0e-122">The default value is Off.</span></span>
    
- <span data-ttu-id="d9c0e-123">**Qualità del servizio vocale (QoS)** Puoi specificare il valore DSCP assegnato al traffico vocale proveniente da un dispositivo Skype for Business Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="d9c0e-123">**Voice Quality of Service (QoS)** You can specify the DSCP value assigned to voice traffic emanating from a Skype for Business Phone Edition device.</span></span> <span data-ttu-id="d9c0e-124">Il valore predefinito è 40.</span><span class="sxs-lookup"><span data-stu-id="d9c0e-124">The default is 40.</span></span> <span data-ttu-id="d9c0e-125">Tuttavia 40 non è il valore normalmente usato per il traffico audio, che in genere è contrassegnato dal codice DSCP 46.</span><span class="sxs-lookup"><span data-stu-id="d9c0e-125">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="d9c0e-126">Per mantenere la coerenza nella rete, è consigliabile modificare questo valore in 46.</span><span class="sxs-lookup"><span data-stu-id="d9c0e-126">In order to maintain consistency throughout your network, you might want to change this value to 46.</span></span>
    
- <span data-ttu-id="d9c0e-127">**Blocco telefono** È possibile specificare se i telefoni UC verranno automaticamente bloccati dopo un periodo di inattività specificato.</span><span class="sxs-lookup"><span data-stu-id="d9c0e-127">**Phone lock** You can specify whether or not UC phones will automatically lock themselves after a specified period of inactivity.</span></span> <span data-ttu-id="d9c0e-128">Di seguito sono descritte le impostazioni che possono essere configurate:</span><span class="sxs-lookup"><span data-stu-id="d9c0e-128">The following are the settings you can configure:</span></span>
    
  - <span data-ttu-id="d9c0e-129">**Applicare il blocco dei dispositivi** Puoi applicare il blocco dei dispositivi selezionando questa casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="d9c0e-129">**Enforce device locking** You can enforce device locking by selecting this check box.</span></span>
    
  - <span data-ttu-id="d9c0e-130">**Lunghezza minima PIN** È possibile specificare la lunghezza minima per il PIN (Personal Identification Number) utilizzato per sbloccare il telefono.</span><span class="sxs-lookup"><span data-stu-id="d9c0e-130">**Minimum PIN length** You can specify the minimum length for the personal identification number (PIN) that is used to unlock the phone.</span></span> <span data-ttu-id="d9c0e-131">L'intervallo di valori per la lunghezza del PIN è compreso tra quattro e 15 numeri.</span><span class="sxs-lookup"><span data-stu-id="d9c0e-131">The range for the PIN length is four to 15 digits.</span></span> <span data-ttu-id="d9c0e-132">La lunghezza predefinita è di sei numeri.</span><span class="sxs-lookup"><span data-stu-id="d9c0e-132">The default length is six digits.</span></span>
    
  - <span data-ttu-id="d9c0e-133">**Timeout blocco telefono** Puoi specificare il periodo di tempo minimo prima che il telefono si blocchi.</span><span class="sxs-lookup"><span data-stu-id="d9c0e-133">**Phone lock time-out** You can specify the minimum length of time before the phone locks itself.</span></span> <span data-ttu-id="d9c0e-134">L'intervallo per il timeout è compreso tra 0 e 60 minuti. il valore predefinito è 10 minuti.</span><span class="sxs-lookup"><span data-stu-id="d9c0e-134">The range for the time-out is 0 to 60 minutes; the default value is 10 minutes.</span></span> <span data-ttu-id="d9c0e-135">Immettere il valore nel formato HH:MM:SS.</span><span class="sxs-lookup"><span data-stu-id="d9c0e-135">Enter the value in the format HH:MM:SS.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d9c0e-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9c0e-136">See also</span></span>

[<span data-ttu-id="d9c0e-137">Configurazione dispositivo</span><span class="sxs-lookup"><span data-stu-id="d9c0e-137">Device Configuration</span></span>](device-configuration.md)

[<span data-ttu-id="d9c0e-138">Set-CsUCPhoneConfiguration</span><span class="sxs-lookup"><span data-stu-id="d9c0e-138">Set-CsUCPhoneConfiguration</span></span>](/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)