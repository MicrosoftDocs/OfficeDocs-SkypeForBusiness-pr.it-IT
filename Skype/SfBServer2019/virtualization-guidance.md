---
title: 'Supporto della virtualizzazione per Skype for Business Server 2019 '
ms.reviewer: corbinm
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Riepilogo: informazioni sul supporto della virtualizzazione per Skype for Business Server 2019.'
ms.openlocfilehash: edced9b0f884cbf76b224c9049cf3498c8f8b45c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509033"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a>Supporto della virtualizzazione per Skype for Business Server 2019

Skype for Business Server 2019 è supportato nella virtualizzazione.

Anche se la virtualizzazione è supportata, esistono alcuni punti chiave da ricordare:

- Mantenere un rapporto di 1:1 tra CPU virtuale e CPU fisica.
- Non spostare un server guest mentre è in funzione.
- La migrazione di un sistema in tempo reale e la portabilità di una macchina virtuale non sono supportate.
- Disabilitare l'hyperthreading in tutti gli host.
- Non configurare la memoria dinamica nei server host.
- Utilizzare dischi fissi o pass-through anziché dischi dinamici.
- Consentire un sovraccarico del 6-10% per gli hypervisor oltre a quello richiesto dal guest virtuale.

## <a name="supported-hypervisors"></a>Hypervisor supportati

SfB Server 2019 è supportato in Windows Server 2016 e Windows Server 2019.

Per gli hypervisor di terze parti, è necessario un hypervisor che abbia superato il test SVVP (Server Virtualization Validation Program) per il sistema operativo pertinente.

- Vedi le [versioni di Windows Server 2016](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) nell'elenco SVVP.
- Vedi le [versioni di Windows Server 2019](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) nell'elenco SVVP.

## <a name="stress-and-performance-tool"></a>Strumento stress e prestazioni

Lo strumento Skype for Business Server 2019 Stress and Performance include strumenti che semplificano la pianificazione della capacità per Skype for Business Server 2019. Lo strumento Skype for Business Server 2019 Stress and Performance consente di:

- Semplificare la pianificazione dell'hardware per Skype for Business Server 2019
- Fornire maggiori conoscenze e procedure consigliate per l'ottimizzazione delle prestazioni
- Misurare le prestazioni delle distribuzioni di Skype for Business Server 2019
 
Puoi scaricare lo strumento da [qui.](https://www.microsoft.com/download/details.aspx?id=101447)
