---
title: 'Supporto per la virtualizzazione di Skype for Business Server 2019 '
ms.reviewer: corbinm
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 06/04/20
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Riepilogo: informazioni sul supporto per la virtualizzazione di Skype for Business Server 2019.'
ms.openlocfilehash: a01f529d80e84df3f7ca844696738b079f78df26
ms.sourcegitcommit: f9db7effbb1e56484686afe4724cc3b73380166d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "44565955"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a>Supporto per la virtualizzazione di Skype for Business Server 2019

Skype for Business Server 2019 è supportato sulla virtualizzazione.

Anche se la virtualizzazione è supportata, esistono alcuni punti chiave da ricordare:

- Mantenere un rapporto di 1:1 tra CPU virtuale e CPU fisica.
- Non spostare un server Guest mentre è in funzione.
- La migrazione di un sistema Live e la portabilità di una macchina virtuale non sono supportate.
- Disabilitare la tecnologia Hyper-Threading su tutti gli host.
- Non configurare la memoria dinamica nei server host.
- Utilizzare dischi fissi o pass-through anziché dischi dinamici.
- Consenti il sovraccarico del 6-10% per gli hypervisor oltre ciò che richiede l'ospite virtuale.

## <a name="supported-hypervisors"></a>Hypervisor supportati

Questo server 2019 è supportato in Windows Server 2016 e Windows Server 2019.

Per le hypervisor di terze parti, è necessario un hypervisor che ha superato il testing del programma SVVP (Server Virtualization Validation Program) per il sistema operativo pertinente.

- Vedere le [versioni di Windows Server 2016](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) nell'elenco SVVP.
- Vedere le [versioni di Windows Server 2019](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) nell'elenco SVVP.
