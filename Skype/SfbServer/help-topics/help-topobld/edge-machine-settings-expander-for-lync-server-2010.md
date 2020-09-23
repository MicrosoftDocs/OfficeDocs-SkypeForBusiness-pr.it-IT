---
title: Espansione delle impostazioni del computer perimetrale per Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: "Per modificare le proprietà dei computer server perimetrali come server perimetrali singoli o come computer membri in un pool di server perimetrali, è necessario configurare le impostazioni di configurazione del nome e dell'indirizzo IP:"
ms.openlocfilehash: eb2135391791fdb915578fe9938329b56c85908c
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218927"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a>Espansione delle impostazioni del computer perimetrale per Lync Server 2010
 
Per modificare le proprietà dei computer server perimetrali come server perimetrali singoli o come computer membri in un pool di server perimetrali, è necessario configurare le impostazioni di **configurazione del nome e dell'indirizzo IP** :
  
- **Nome interno o FQDN**: digitare il nome del computer in cui viene fatto riferimento nel DNS (Domain Name System). 
    
- **Indirizzo IPv4 interno**: digitare l'indirizzo IPv4 della scheda di interfaccia di rete (NIC) interna del computer.
    
- È possibile configurare l' **indirizzo IPv4 esterno** del **servizio Access Edge** associato al computer
    
    > [!IMPORTANT]
    > Se si è scelto di utilizzare un singolo indirizzo IP per la configurazione del server perimetrale, sarà possibile modificare solo l'indirizzo IPv4 esterno per il servizio Access Edge. Gli altri servizi perimetrali condivideranno lo stesso indirizzo IPv4 del servizio Access Edge. 
  
- Se è disponibile per la modifica, è possibile configurare l' **indirizzo IPv4 esterno** del **servizio Web Conferencing** associato a questo computer.
    
- Se è disponibile per la modifica, è possibile configurare l' **indirizzo IPv4 esterno** del **servizio a/V Edge** associato a questo computer.
    
- Se è disponibile per la modifica, è possibile configurare l' **indirizzo IPv4 pubblico abilitato NAT** associato a questo computer.
    
    > [!IMPORTANT]
    > Se si è scelto di fornire NAT (Network Address Translation) per il servizio A/V Edge, la proprietà di configurazione per l' **indirizzo IPv4 pubblico abilitato per NAT** sarà disponibile solo per la modifica.
  
  **OK** Accetta le modifiche apportate nella finestra di dialogo e ne esegue il commit.
  
  **Annulla** Rimuove le modifiche e chiude la finestra di dialogo.
  
  **?** Visualizza questa schermata della Guida.
  

