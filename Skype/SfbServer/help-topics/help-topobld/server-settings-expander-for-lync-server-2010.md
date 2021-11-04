---
title: Espansione delle impostazioni del server per Lync Server 2010
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: 'Ecco come fare per modificare le proprietà per questo computer:'
ms.openlocfilehash: 599f041a1428ae1b418141ef7ce8779c7eba06fa
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765674"
---
# <a name="server-settings-expander-for-lync-server-2010"></a>Espansione delle impostazioni del server per Lync Server 2010
 
Ecco come fare per modificare le proprietà per questo computer:
  
- Modificare l'impostazione **Nome di dominio completo (FQDN)** per questo computer. Questa voce deve corrispondere al nome del computer così come è stato definito in DNS (Domain Name System) e nei nomi alternativi del soggetto (SAN) o nel nome soggetto (SN) del certificato associato al computer.
    
- Selezionare una di queste opzioni:
    
    **Usa tutti gli indirizzi IP configurati**: selezionare questa opzione per usare tutti gli indirizzi IP configurati nel computer.
    
    > [!IMPORTANT]
    > Se il computer ha più indirizzi IP, è necessario tenere presente che i servizi associati al computer useranno tutti gli indirizzi IP per tutti i servizi. Se un server o un servizio di attesa attende le comunicazioni di una porta e un indirizzo IP specifici, il servizio potrebbe non selezionare nel modo migliore l'indirizzo IP su cui restare in attesa. 
  
    **Limita utilizzo servizio a indirizzi IP selezionati**: selezionare questa opzione se si vuole definire indirizzi IP specifici in **Indirizzo IP primario** per l'indirizzo IP primario su cui il computer resterà in attesa delle comunicazioni da altri computer e pool nella distribuzione. Definire **Indirizzo IP PSTN** per l'indirizzo IP specifico su cui il computer o il servizio resteranno in attesa delle comunicazioni e invieranno le comunicazioni al gateway PSTN o all'IP-PBX definito.
    

