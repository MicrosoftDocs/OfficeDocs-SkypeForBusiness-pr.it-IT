---
title: Testare le impostazioni di configurazione dei trunk SIP in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Le impostazioni di configurazione dei trunk SIP consentono di definire le funzionalità e la relazione tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un sistema IP-PBX o un servizio Session Border Controller (SBC) nel provider di servizi. '
ms.openlocfilehash: 87f5b8aa07a7545f30f1d0e8b81b33197ea704c1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103022"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="fc14f-103">Testare le impostazioni di configurazione dei trunk SIP in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fc14f-103">Test SIP trunk configuration settings in Skype for Business Server</span></span>

<span data-ttu-id="fc14f-p101">Le impostazioni di configurazione dei trunk SIP consentono di definire le funzionalità e la relazione tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un sistema IP-PBX o un servizio Session Border Controller (SBC) nel provider di servizi. Queste impostazioni consentono di specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="fc14f-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

- <span data-ttu-id="fc14f-106">Se abilitare il bypass multimediale nei trunk.</span><span class="sxs-lookup"><span data-stu-id="fc14f-106">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="fc14f-107">Le condizioni in base alle quali vengono inviati pacchetti RTCP (Real-Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="fc14f-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="fc14f-108">Se in ogni trunk è richiesta la crittografia SRTP (Secure Real-Time Protocol).</span><span class="sxs-lookup"><span data-stu-id="fc14f-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="fc14f-109">Quando si installa Skype for Business Server, viene creata automaticamente una raccolta globale di impostazioni di configurazione trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="fc14f-109">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="fc14f-110">Gli amministratori inoltre possono creare raccolte di impostazioni personalizzate nell'ambito del sito o del servizio (solo per il servizio gateway PSTN).</span><span class="sxs-lookup"><span data-stu-id="fc14f-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="fc14f-111">Gli amministratori possono inoltre utilizzare il cmdlet [Test-CsTrunkConfiguration](/powershell/module/skype/Test-CsTrunkConfiguration) per verificare che un trunk sia in grado di convertire un numero composto da un utente in un numero che può essere gestito dal gateway.</span><span class="sxs-lookup"><span data-stu-id="fc14f-111">Administrators can also use the [Test-CsTrunkConfiguration](/powershell/module/skype/Test-CsTrunkConfiguration) cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>

<span data-ttu-id="fc14f-112">Le impostazioni di configurazione dei trunk possono essere verificate solo utilizzando Windows PowerShell e il cmdlet Test-CsTrunkConfiguration.</span><span class="sxs-lookup"><span data-stu-id="fc14f-112">Trunk configuration settings can only be tested by using Windows PowerShell and the Test-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="fc14f-113">Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fc14f-113">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

<span data-ttu-id="fc14f-114">**Per testare le impostazioni di configurazione dei trunk SIP**</span><span class="sxs-lookup"><span data-stu-id="fc14f-114">**To test SIP trunk configuration settings**</span></span>

<span data-ttu-id="fc14f-115">Il comando seguente verifica che le impostazioni di configurazione dei trunk per il sito Redmond siano in grado di convertire correttamente il numero composto 4255551212.</span><span class="sxs-lookup"><span data-stu-id="fc14f-115">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>

```PowerShell
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```