---
title: Aggiornare AAD Connect per includere più di una foresta
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Questa appendice include la procedura dettagliata per l'aggiornamento di AAD Connessione in modo da includere più foreste come parte del consolidamento cloud per Teams e Skype for Business.
ms.openlocfilehash: 5ca5789ca50f24266ce5fccf16bcf06118e42742
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2021
ms.locfileid: "53510527"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a>Aggiornare AAD Connect per includere più di una foresta

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Azure AD Connessione supporta la [sincronizzazione da più foreste.](/azure/active-directory/connect/active-directory-aadconnect-topologies) Tuttavia, supporta una sola istanza di Azure AD Connessione sincronizzazione con AAD. Pertanto, nei casi in cui Azure AD è già installato in una foresta, l'istanza esistente di AAD Connessione deve essere aggiornata per la sincronizzazione dalla foresta aggiuntiva.

 - Se tutte le identità sono rappresentate una sola volta in entrambe le foreste,ovvero non sono stati effettuati contatti abilitati alla posta elettronica, è sufficiente eseguire di nuovo la procedura guidata di Connessione di AAD, scegliere "Personalizza opzioni di sincronizzazione" e quindi nella pagina Directory personali di **Connessione** immettere il nome della foresta e delle identità aggiuntive.<br><br>
 ![Pagina Connessione directory](../media/cloud-consolidation-connect-your-directories.png)
 - Tuttavia, se gli utenti possono esistere in più directory e si uniranno i dati (ad esempio, se gli oggetti contatto sono presenti in una foresta corrispondente agli utenti in un'altra foresta), sarà necessario disinstallare Azure AD Connessione e reinstallarlo.  Ciò è dovuto al fatto che la condizione delle regole di join tra foreste può essere configurata solo durante la prima installazione. Questa operazione viene eseguita nella pagina seguente:<br><br>
 ![Pagina Identificazione univoca degli utenti](../media/cloud-consolidation-uniquely-identifying-your-users.png)


## <a name="see-also"></a>Vedere anche

[Consolidamento cloud per Teams e Skype for Business](cloud-consolidation.md)