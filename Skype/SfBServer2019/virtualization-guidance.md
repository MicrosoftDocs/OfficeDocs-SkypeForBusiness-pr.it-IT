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
ms.openlocfilehash: 61b54a7e2d8fc170fe63137f637246f56dcce2a01dc7af0b41ea6dc5c5c56099
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54334558"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a>Supporto della virtualizzazione per Skype for Business Server 2019

Skype for Business Server 2019 è supportato nella virtualizzazione.

Anche se la virtualizzazione è supportata, esistono alcuni punti chiave da ricordare:

- Mantenere un rapporto 1:1 tra CPU virtuale e CPU fisica.
- Non spostare un server guest mentre è in funzione.
- La migrazione di un sistema in tempo reale e la portabilità di una macchina virtuale non sono supportate.
- Disabilitare l'hyperthreading in tutti gli host.
- Non configurare la memoria dinamica nei server host.
- Utilizzare dischi fissi o pass-through anziché dischi dinamici.
- Consentire un sovraccarico del 6-10% per gli hypervisor oltre a quello richiesto dal guest virtuale.

## <a name="supported-hypervisors"></a>Hypervisor supportati

SfB Server 2019 è supportato in Windows Server 2016 e Windows Server 2019.

Per gli hypervisor di terze parti, è necessario un hypervisor che abbia superato il test SVVP (Server Virtualization Validation Program) per il sistema operativo pertinente.

- Vedi le [Windows Server 2016 nell'elenco](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) SVVP.
- Vedere le [Windows Server 2019](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) nell'elenco SVVP.

## <a name="stress-and-performance-tool"></a>Strumento stress e prestazioni

Lo Skype for Business Server 2019 Stress and Performance Tool include strumenti che semplificano la pianificazione della capacità Skype for Business Server 2019. Lo Skype for Business Server 2019 Stress and Performance Tool consente di:

- Semplificare la pianificazione dell'hardware Skype for Business Server 2019
- Fornire conoscenze e procedure consigliate per l'ottimizzazione delle prestazioni
- Misurare le prestazioni delle distribuzioni Skype for Business Server 2019
 
È possibile scaricare lo strumento da [qui](https://www.microsoft.com/download/details.aspx?id=101447).
