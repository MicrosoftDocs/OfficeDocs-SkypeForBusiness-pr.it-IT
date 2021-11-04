---
title: Espansione delle impostazioni dell'FQDN del server perimetrale per Lync Server 2010
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
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 'Per definire le proprietà in Impostazioni esterne, configurare queste opzioni:'
ms.openlocfilehash: 505a4607029ccef38bb937cbb44891f9baaf3eb4
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60772232"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a>Espansione delle impostazioni del nome di dominio completo (FQDN) del server perimetrale per Lync Server 2010
 
Per definire le proprietà in **Impostazioni esterne**, configurare queste opzioni:
  
Selezionare la casella di controllo **Abilita FQDN e indirizzo IP distinti per Web Conferencing e A/V** se si desidera definire FQDN e indirizzi IP distinti per le conferenze Web e le funzionalità audio/video.
  
> [!NOTE]
> Se si sceglie di non selezionare la casella di controllo per fqdn e indirizzi IP separati, è necessario fornire porte distinte per ognuno dei tre servizi forniti dal server perimetrale. L'unico nome di dominio completo da configurare è il nome di dominio completo associato al servizio Access Edge. 
  
Selezionare la casella di controllo **A/V Edge service is NAT enabled** se si desidera che il servizio A/V Edge utilizzi un indirizzo IP NAT (Network Address Translation) e una configurazione.
  
Per i servizi Edge abilitati, digitare un FQDN in **FQDN pool** e una porta in **Porte**
  
- Definire l'FQDN del pool per **Servizio Access Edge** e una porta che identifichi in modo univoco il servizio.
    
- Definire l'FQDN del pool per **Servizio Web Conferencing Edge** (se la casella di controllo Abilita FQDN e indirizzo IP distinti per Web Conferencing e A/V è deselezionata) e una porta che identifichi in modo univoco il servizio.
    
- Definire l'FQDN del pool per **Servizio A/V Edge** (se la casella di controllo Abilita FQDN e indirizzo IP distinti per Web Conferencing e A/V è deselezionata) e una porta che identifichi in modo univoco il servizio.
    
  **OK** Accetta le modifiche apportate nella finestra di dialogo e ne esegue il commit.
  
  **Annulla** Rimuove le modifiche e chiude la finestra di dialogo.
  
  **?** Visualizza questa schermata della Guida.
  

