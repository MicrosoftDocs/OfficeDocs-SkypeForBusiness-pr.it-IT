---
title: Espansione delle impostazioni di Mediation Server per Lync Server 2010
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
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 'In questa finestra di dialogo è possibile modificare le proprietà dei Mediation Server. Sul lato sinistro è presente un insieme di collegamenti rapidi che consentono di accedere alle impostazioni delle sezioni Generale, Hop successivo e Gateway PSTN. In ogni sezione sono disponibili le impostazioni seguenti:'
ms.openlocfilehash: 87eda891ae5c9e19a9a54e000b85b62e46c077d6a4c90318c9372fe6e887ecaa
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344785"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a>Espansione delle impostazioni di Mediation Server per Lync Server 2010

In questa finestra di dialogo è possibile modificare le proprietà dei Mediation Server. Sul lato sinistro è presente un insieme di collegamenti rapidi che consentono di accedere alle impostazioni delle sezioni Generale, Hop successivo e Gateway PSTN. In ogni sezione sono disponibili le impostazioni seguenti:

 **Generale**:

- **FQDN**: modificare il nome di dominio completo del Mediation Server

- **Associazioni**: selezionare la casella di controllo Associa pool di server perimetrali (per i componenti **multimediali)** e selezionare un server perimetrale o un pool di server perimetrali per il Mediation Server da utilizzare come percorso multimediale per l'accesso esterno.

  **Hop successivo**:

- **Selezione hop successivo:** selezionare da un elenco il Front End Server o il pool Front End da utilizzare come percorso per il Mediation Server da utilizzare per comunicare con la distribuzione.

  **Gateway PSTN**:

  **Gateway PSTN Mediation Server**:

- **Porte di attesa:** definire le porte su cui il Mediation Server sarà in ascolto. È possibile definire una porta per **TLS** (Transport Layer Security) o **TCP** (Transport Control Protocol). Per rendere disponibile la voce della porta relativa a TCP, è necessario selezionare la casella di controllo **Abilita porta TCP**.

    > [!IMPORTANT]
    > Consultare la documentazione e le impostazioni di configurazione del gateway PSTN (Public Switched Telephone Network) per determinare se è necessario abilitare e definire i valori di porta TLS, TCP o entrambi. TLS è un protocollo più sicuro, che utilizza certificati per crittografare il traffico tra Mediation Server e il gateway PSTN. Non tutti i gateway PSTN supportano TLS.

- Di seguito sono elencati i trunk SIP e i gateway definiti e configurati per la distribuzione corrente. Se non è presente alcuna voce, significa che non ci sono trunk SIP o gateway PSTN configurati per la distribuzione. È possibile definire e configurare trunk e gateway in **Componenti condivisi** in Generatore di topologie.

## <a name="see-also"></a>Vedere anche

[Panoramica del trunking SIP](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-sip-trunking)

[Opzioni di distribuzione del gateway PSTN](/previous-versions/office/lync-server-2013/lync-server-2013-pstn-gateway-deployment-options)