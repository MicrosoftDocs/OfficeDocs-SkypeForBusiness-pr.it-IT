---
title: Expander di impostazioni server per Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: 'Per modificare le proprietà di questo computer, eseguire le operazioni seguenti:'
ms.openlocfilehash: 28261b3637040acda70218f23101b4337b1f90c3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194965"
---
# <a name="server-settings-expander-for-lync-server-2010"></a>Expander di impostazioni server per Lync Server 2010
 
Per modificare le proprietà di questo computer, eseguire le operazioni seguenti:
  
- Modificare il **nome di dominio completo (FQDN)** per il computer. Questa voce deve corrispondere al nome del computer in quanto è definita nel DNS (Domain Name System) e in nomi alternativi oggetto (SAN) o nome soggetto (SN) del certificato associato al computer.
    
- Si seleziona una delle opzioni seguenti:
    
    **Usare tutti gli indirizzi IP**configurati: selezionare questa funzionalità per usare tutti gli indirizzi IP configurati nel computer.
    
    > [!IMPORTANT]
    > Se nel computer sono presenti più indirizzi IP, è necessario tenere presente che i servizi associati al computer utilizzeranno tutti gli indirizzi IP per tutti i servizi. Se un server o un servizio di ascolto si aspetta la comunicazione di un determinato indirizzo IP e una porta, il servizio potrebbe non eseguire la selezione ottimale dell'indirizzo IP da ascoltare. 
  
    **Limitare l'utilizzo del servizio agli indirizzi IP selezionati**: selezionare questa opzione se si desidera definire indirizzi IP specifici per l' **indirizzo IP principale** che questo computer potrà ascoltare per comunicare da altri computer e pool nella distribuzione. Definisci l' **indirizzo IP PSTN** per l'indirizzo IP specifico che il computer e il servizio ascolteranno per le comunicazioni e invieranno comunicazioni al gateway PSTN o IP-PBX definito.
    

