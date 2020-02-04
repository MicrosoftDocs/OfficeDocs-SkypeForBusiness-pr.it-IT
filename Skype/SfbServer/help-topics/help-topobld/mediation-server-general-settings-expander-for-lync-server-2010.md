---
title: Espansione delle impostazioni generali di Mediation Server per Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 'Modificare le proprietà dei server di mediazione in questa finestra di dialogo. Lungo il lato sinistro è presente un set di collegamenti rapidi che consente di eseguire le impostazioni per le impostazioni generali, le impostazioni hop successivo e le impostazioni del gateway PSTN. In ogni sezione sono disponibili le impostazioni seguenti:'
ms.openlocfilehash: d439698bf0e383f9c89fb749ef4cedc7ae253997
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684549"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a>Espansione delle impostazioni generali di Mediation Server per Lync Server 2010

Modificare le proprietà dei server di mediazione in questa finestra di dialogo. Lungo il lato sinistro è presente un set di collegamenti rapidi che consente di eseguire le impostazioni per le impostazioni generali, le impostazioni hop successivo e le impostazioni del gateway PSTN. In ogni sezione sono disponibili le impostazioni seguenti:

 **Generale**:

- **FQDN**: si modifica il nome di dominio completo del Mediation Server

- **Associazioni**: selezionare la casella di controllo **Associa pool Edge (per componenti multimediali)** e selezionare un server perimetrale o un pool di Edge per il Mediation Server da usare come percorso multimediale per l'accesso esterno.

  **Hop successivo**:

- **Selezione hop successivo**: selezionare da un elenco il front end server o il pool Front end da usare come percorso per il server di mediazione da usare per comunicare con la distribuzione.

  **Gateway PSTN**:

  **Gateway PSTN di Mediation Server**:

- **Porte in ascolto**: definire le porte che il server di mediazione ascolterà. Puoi definire una porta per **TLS** o Transport Layer Security o **TCP**o Transport Control Protocol. Per rendere disponibile la voce di porta per TCP, è necessario selezionare la casella di controllo **Abilita porta TCP**.

    > [!IMPORTANT]
    > Fare riferimento alla documentazione e alle impostazioni di configurazione per il gateway PSTN (Public Switched Telephone Network) per determinare se è necessario abilitare e definire i valori di porta TLS, TCP o entrambi. TLS è un protocollo più sicuro, usando i certificati per crittografare il traffico tra il Mediation Server e il gateway PSTN. Non tutti i gateway PSTN supportano TLS.

- Un elenco di trunk SIP e i gateway definiti e configurati per la distribuzione sono elencati. Se non sono presenti voci, non ci sono trunk SIP o gateway PSTN configurati per la distribuzione. Si definiscono e si configurano trunk e gateway in **componenti condivisi** in Generatore di topologia.

## <a name="see-also"></a>Vedere anche

[Panoramica del trunking SIP](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[Opzioni di distribuzione del gateway PSTN](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)
