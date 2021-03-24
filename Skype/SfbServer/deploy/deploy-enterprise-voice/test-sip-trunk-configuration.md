---
title: Testare le impostazioni di configurazione dei trunk SIP in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: 'Riepilogo: informazioni su come testare le impostazioni di configurazione dei trunk SIP tramite Skype for Business Server Management Shell.'
ms.openlocfilehash: 6f569c7e397e7902cb347e13b4077acb5a9b34fb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103372"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="c3928-103">Testare le impostazioni di configurazione dei trunk SIP in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c3928-103">Test SIP trunk configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="c3928-104">**Riepilogo:** Informazioni su come testare le impostazioni di configurazione dei trunk SIP tramite Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c3928-104">**Summary:** Learn how to test SIP trunk configuration settings by using the Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="c3928-105">Le impostazioni di configurazione trunk SIP definiscono la relazione e le funzionalità tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un PBX (Branch eXchange) di IP-Public o un session border controller (SBC) presso il provider di servizi.</span><span class="sxs-lookup"><span data-stu-id="c3928-105">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the Public Switched Telephone Network (PSTN) gateway, an IP-Public Branch eXchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="c3928-106">Queste impostazioni consentono di specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="c3928-106">These settings do such things as specify:</span></span>
  
- <span data-ttu-id="c3928-107">Se abilitare il bypass multimediale nei trunk.</span><span class="sxs-lookup"><span data-stu-id="c3928-107">Whether media bypass should be enabled on the trunks.</span></span>
    
- <span data-ttu-id="c3928-108">Condizioni in base alle quali vengono inviati i pacchetti RTCP (Realtime Transport Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="c3928-108">The conditions under which Realtime Transport Control Protocol (RTCP) packets are sent.</span></span>
    
- <span data-ttu-id="c3928-109">Indica se è necessaria o meno la crittografia SRTP (Secure Realtime Transport Protocol) in ogni trunk.</span><span class="sxs-lookup"><span data-stu-id="c3928-109">Whether or not Secure Realtime Transport Protocol (SRTP) encryption is required on each trunk.</span></span>
    
<span data-ttu-id="c3928-110">Quando si installa Skype for Business Server, viene creata automaticamente una raccolta globale di impostazioni di configurazione trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="c3928-110">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="c3928-111">Gli amministratori inoltre possono creare raccolte di impostazioni personalizzate nell'ambito del sito o del servizio (solo per il servizio gateway PSTN).</span><span class="sxs-lookup"><span data-stu-id="c3928-111">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="c3928-112">Gli amministratori possono anche utilizzare il cmdlet Test-CsTrunkConfiguration per verificare che un trunk sia in grado di convertire un numero composto da un utente in un numero gestibile dal gateway.</span><span class="sxs-lookup"><span data-stu-id="c3928-112">Administrators can also use the Test-CsTrunkConfiguration cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>
  
<span data-ttu-id="c3928-113">Le impostazioni di configurazione dei trunk possono essere verificate solo utilizzando Windows PowerShell e il cmdlet [Test-CsTrunkConfiguration](/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="c3928-113">Trunk configuration settings can only be tested by using Windows PowerShell and the [Test-CsTrunkConfiguration](/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="c3928-114">Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c3928-114">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Skype for Business Server Management Shell.</span></span>
  
### <a name="to-test-sip-trunk-configuration-settings"></a><span data-ttu-id="c3928-115">Per testare le impostazioni di configurazione dei trunk SIP</span><span class="sxs-lookup"><span data-stu-id="c3928-115">To test SIP trunk configuration settings</span></span>

- <span data-ttu-id="c3928-116">Il comando seguente verifica che le impostazioni di configurazione dei trunk per il sito Redmond siano in grado di convertire correttamente il numero composto 4255551212.</span><span class="sxs-lookup"><span data-stu-id="c3928-116">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>
    
  ```powershell
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```