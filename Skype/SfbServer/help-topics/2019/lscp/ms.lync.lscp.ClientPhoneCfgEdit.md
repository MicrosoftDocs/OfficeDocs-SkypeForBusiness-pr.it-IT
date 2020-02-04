---
title: Configurazione del dispositivo crea nuovi o modifica esistenti
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
ROBOTS: NOINDEX, NOFOLLOW
description: Nella pagina Configurazione nuovo dispositivo o modifica dispositivo è possibile creare o modificare una raccolta di impostazioni usate per gestire Skype for Business Phone Edition. Queste impostazioni consentono di configurare aspetti come la modalità di sicurezza richiesta, il livello di registrazione dei dispositivi, le impostazioni di Qualità del servizio (QoS) e il blocco automatico dei telefoni dopo un periodo di inattività specificato.
ms.openlocfilehash: fce3ad1410dc16cc6a238823f11cdba0f4c4c391
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41691481"
---
# <a name="device-configuration-create-new-or-edit-existing"></a><span data-ttu-id="15163-104">Configurazione dispositivo: crearne una nuova o modificarne una esistente</span><span class="sxs-lookup"><span data-stu-id="15163-104">Device Configuration: Create New or Edit Existing</span></span>
 
<span data-ttu-id="15163-105">Nella pagina configurazione **nuovo dispositivo** o **modifica dispositivo** è possibile creare o modificare una raccolta di impostazioni usate per gestire Skype for Business Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="15163-105">On the **New Device Configuration** or **Edit Device Configuration** page, you can create or modify a collection of settings used to manage Skype for Business Phone Edition.</span></span> <span data-ttu-id="15163-106">Queste impostazioni consentono di configurare aspetti come la modalità di sicurezza richiesta, il livello di registrazione dei dispositivi, le impostazioni di Qualità del servizio (QoS) e il blocco automatico dei telefoni dopo un periodo di inattività specificato.</span><span class="sxs-lookup"><span data-stu-id="15163-106">These settings enable you to configure such things as the required security mode, device logging level, Voice Quality of Service (QoS) settings, and whether or not phones should automatically lock after a specified period of inactivity.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="15163-107">Attività che è possibile eseguire</span><span class="sxs-lookup"><span data-stu-id="15163-107">Tasks you can perform</span></span>

<span data-ttu-id="15163-108">Nella pagina **Nuova configurazione dispositivo** o **Modifica configurazione dispositivo** è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="15163-108">You can perform the following tasks on the **New Device Configuration** or **Edit Device Configuration** page:</span></span>
  
- <span data-ttu-id="15163-109">Aggiungere una nuova configurazione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="15163-109">Add a new device configuration.</span></span>
    
- <span data-ttu-id="15163-110">Modificare le proprietà di una configurazione del dispositivo esistente.</span><span class="sxs-lookup"><span data-stu-id="15163-110">Modify the properties of an existing device configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="15163-111">Riferimenti UI</span><span class="sxs-lookup"><span data-stu-id="15163-111">UI Reference</span></span>

<span data-ttu-id="15163-112">Gli elenchi seguenti descrivono i menu, i comandi, i campi e le proprietà della pagina.</span><span class="sxs-lookup"><span data-stu-id="15163-112">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="15163-113">**Ambito** Identifica l'ambito (globale o sito) della configurazione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="15163-113">**Scope** Identifies the scope (Global or Site) of the device configuration.</span></span>
    
- <span data-ttu-id="15163-114">**Nome** È possibile aggiungere o modificare il nome della configurazione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="15163-114">**Name** You can add or modify the name of the device configuration.</span></span>
    
- <span data-ttu-id="15163-115">**Sicurezza SIP** È possibile configurare i requisiti di trasporto e autenticazione per i dispositivi Skype for Business Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="15163-115">**SIP security** You can configure transport and authentication requirements for Skype for Business Phone Edition devices.</span></span> <span data-ttu-id="15163-116">È possibile scegliere tra le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="15163-116">You can select from the following options:</span></span>
    
  - <span data-ttu-id="15163-117">**Basso** Consentire qualsiasi tipo di autorizzazione o trasporto.</span><span class="sxs-lookup"><span data-stu-id="15163-117">**Low** Allow any type of authorization or transport.</span></span>
    
  - <span data-ttu-id="15163-118">**Medio** È necessario NTLM o Kerberos per l'autenticazione utente.</span><span class="sxs-lookup"><span data-stu-id="15163-118">**Medium** NTLM or Kerberos is required for user authentication.</span></span>
    
  - <span data-ttu-id="15163-119">**Alto** È necessario NTLM o Kerberos per l'autenticazione dell'utente e TLS è necessario per le connessioni SIP.</span><span class="sxs-lookup"><span data-stu-id="15163-119">**High** NTLM or Kerberos is required for user authentication and TLS is required for SIP connections.</span></span>
    
- <span data-ttu-id="15163-120">**Livello di registrazione** È possibile abilitare la registrazione nel dispositivo UC.</span><span class="sxs-lookup"><span data-stu-id="15163-120">**Logging level** You can enable logging on the UC device.</span></span> <span data-ttu-id="15163-121">I valori validi sono Disattivato, Basso, Medio e Alto.</span><span class="sxs-lookup"><span data-stu-id="15163-121">Valid values are: Off; Low; Medium; and High.</span></span> <span data-ttu-id="15163-122">Il valore predefinito è Disattivato.</span><span class="sxs-lookup"><span data-stu-id="15163-122">The default value is Off.</span></span>
    
- <span data-ttu-id="15163-123">**Qualità del servizio (QoS) vocale** Puoi specificare il valore DSCP assegnato al traffico vocale proveniente da un dispositivo Skype for Business Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="15163-123">**Voice Quality of Service (QoS)** You can specify the DSCP value assigned to voice traffic emanating from a Skype for Business Phone Edition device.</span></span> <span data-ttu-id="15163-124">Il valore predefinito è 40.</span><span class="sxs-lookup"><span data-stu-id="15163-124">The default is 40.</span></span> <span data-ttu-id="15163-125">Tuttavia 40 non è il valore normalmente usato per il traffico audio, che in genere è contrassegnato dal codice DSCP 46.</span><span class="sxs-lookup"><span data-stu-id="15163-125">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="15163-126">Per mantenere la coerenza nella rete, è consigliabile modificare questo valore in 46.</span><span class="sxs-lookup"><span data-stu-id="15163-126">In order to maintain consistency throughout your network, you might want to change this value to 46.</span></span>
    
- <span data-ttu-id="15163-127">**Blocco telefono** È possibile specificare se i telefoni UC si bloccano automaticamente dopo un periodo di inattività specificato.</span><span class="sxs-lookup"><span data-stu-id="15163-127">**Phone lock** You can specify whether or not UC phones will automatically lock themselves after a specified period of inactivity.</span></span> <span data-ttu-id="15163-128">Di seguito sono descritte le impostazioni che possono essere configurate:</span><span class="sxs-lookup"><span data-stu-id="15163-128">The following are the settings you can configure:</span></span>
    
  - <span data-ttu-id="15163-129">**Applicare il blocco del dispositivo** È possibile applicare il blocco del dispositivo selezionando questa casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="15163-129">**Enforce device locking** You can enforce device locking by selecting this check box.</span></span>
    
  - <span data-ttu-id="15163-130">**Lunghezza minima del pin** È possibile specificare la lunghezza minima per il PIN (Personal Identification Number) usato per sbloccare il telefono.</span><span class="sxs-lookup"><span data-stu-id="15163-130">**Minimum PIN length** You can specify the minimum length for the personal identification number (PIN) that is used to unlock the phone.</span></span> <span data-ttu-id="15163-131">L'intervallo di valori per la lunghezza del PIN è compreso tra quattro e 15 cifre.</span><span class="sxs-lookup"><span data-stu-id="15163-131">The range for the PIN length is four to 15 digits.</span></span> <span data-ttu-id="15163-132">La lunghezza predefinita è di sei cifre.</span><span class="sxs-lookup"><span data-stu-id="15163-132">The default length is six digits.</span></span>
    
  - <span data-ttu-id="15163-133">**Timeout blocco telefono** È possibile specificare il periodo di tempo minimo prima che il telefono si blocchi.</span><span class="sxs-lookup"><span data-stu-id="15163-133">**Phone lock time-out** You can specify the minimum length of time before the phone locks itself.</span></span> <span data-ttu-id="15163-134">L'intervallo per il timeout è compreso tra 0 e 60 minuti; il valore predefinito è di 10 minuti.</span><span class="sxs-lookup"><span data-stu-id="15163-134">The range for the time-out is 0 to 60 minutes; the default value is 10 minutes.</span></span> <span data-ttu-id="15163-135">Immettere il valore nel formato HH: MM: SS.</span><span class="sxs-lookup"><span data-stu-id="15163-135">Enter the value in the format HH:MM:SS.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="15163-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15163-136">See also</span></span>

[<span data-ttu-id="15163-137">Configurazione dispositivo</span><span class="sxs-lookup"><span data-stu-id="15163-137">Device Configuration</span></span>](ms.lync.lscp.ClientDeviceCfgMain.md)

[<span data-ttu-id="15163-138">Set-CsUCPhoneConfiguration</span><span class="sxs-lookup"><span data-stu-id="15163-138">Set-CsUCPhoneConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)
