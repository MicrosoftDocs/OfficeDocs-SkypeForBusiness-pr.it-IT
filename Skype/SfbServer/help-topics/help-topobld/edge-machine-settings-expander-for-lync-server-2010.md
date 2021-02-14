---
title: Espansione delle impostazioni del computer perimetrale per Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: "Per modificare le proprietà dei computer server perimetrali come singolo server perimetrale o come computer membri in un pool di server perimetrali, configurare le impostazioni di configurazione del nome server e dell'indirizzo IP:"
ms.openlocfilehash: e25f68ec510cf15cd58872a8c584dc71aa939f48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807136"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a>Espansione delle impostazioni del computer perimetrale per Lync Server 2010
 
Per modificare le proprietà dei computer server perimetrali come singolo server perimetrale o come computer membri in un pool di server perimetrali, configurare le impostazioni di configurazione del nome server e **dell'indirizzo IP:**
  
- **Nome interno o FQDN:** digitare il nome del computer a cui si fa riferimento nel DNS (Domain Name System). 
    
- **Indirizzo IPv4 interno:** digitare l'indirizzo IPv4 della scheda nic (Network Interface Card) interna del computer.
    
- Configurare l'indirizzo **IPv4 esterno** del servizio **Access Edge** associato al computer
    
    > [!IMPORTANT]
    > Se si è scelto di utilizzare un singolo indirizzo IP per la configurazione del server perimetrale, sarà possibile modificare solo l'indirizzo IPv4 esterno per il servizio Access Edge. Gli altri servizi Edge condivideranno lo stesso indirizzo IPv4 del servizio Access Edge. 
  
- Se disponibile per la modifica, configurare l'indirizzo **IPv4** esterno del servizio **Web Conferencing** associato al computer
    
- Se disponibile per la modifica, configurare l'indirizzo **IPv4** esterno del servizio **A/V Edge** associato al computer
    
- Se disponibile per la modifica, configurare l'indirizzo **IPv4** pubblico abilitato per NAT associato al computer.
    
    > [!IMPORTANT]
    > La proprietà di configurazione per l'indirizzo **IPv4** pubblico abilitato per NAT sarà disponibile per la modifica solo se si è scelto di fornire nat (Network Address Translation) per il servizio A/V Edge
  
  **OK** Accetta le modifiche apportate nella finestra di dialogo e ne esegue il commit.
  
  **Annulla** Rimuove le modifiche e chiude la finestra di dialogo.
  
  **?** Visualizza questa schermata della Guida.
  

