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
description: 'È possibile modificare le proprietà dei Mediation Server in questa finestra di dialogo. Sul lato sinistro è presente un insieme di collegamenti rapidi che consentono di accedere alle impostazioni delle sezioni Generale, Hop successivo e Gateway PSTN. In ogni sezione sono disponibili le impostazioni seguenti:'
ms.openlocfilehash: db7964826a50f462435769d66ddfab3804462541
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806746"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a>Espansione delle impostazioni di Mediation Server per Lync Server 2010

È possibile modificare le proprietà dei Mediation Server in questa finestra di dialogo. Sul lato sinistro è presente un insieme di collegamenti rapidi che consentono di accedere alle impostazioni delle sezioni Generale, Hop successivo e Gateway PSTN. In ogni sezione sono disponibili le impostazioni seguenti:

 **Generale**:

- **FQDN**: è possibile modificare il nome di dominio completo del Mediation Server

- **Associazioni**: selezionare la casella di controllo **Associa pool di server perimetrali (per componenti multimediali)** e selezionare un perimetro o un pool perimetrale per il Mediation Server da utilizzare come percorso multimediale per l'accesso esterno.

  **Hop successivo**:

- **Selezione hop successivo**: selezionare da un elenco il front end server o il pool Front end da utilizzare come percorso per il Mediation Server da utilizzare per la comunicazione con la distribuzione.

  **Gateway PSTN**:

  **Gateway PSTN Mediation Server**:

- **Porte di attesa**: consente di definire le porte che il Mediation server ascolterà. È possibile definire una porta per **TLS** (Transport Layer Security) o **TCP** (Transport Control Protocol). Per rendere disponibile la voce della porta relativa a TCP, è necessario selezionare la casella di controllo **Abilita porta TCP**.

    > [!IMPORTANT]
    > Consultare la documentazione e le impostazioni di configurazione del gateway PSTN (Public Switched Telephone Network) per determinare se è necessario abilitare e definire i valori di porta TLS, TCP o entrambi. TLS è un protocollo più sicuro, utilizzando i certificati per crittografare il traffico tra il Mediation Server e il gateway PSTN. Non tutti i gateway PSTN supportano TLS.

- Di seguito sono elencati i trunk SIP e i gateway definiti e configurati per la distribuzione corrente. Se non è presente alcuna voce, significa che non ci sono trunk SIP o gateway PSTN configurati per la distribuzione. I trunk e i gateway vengono definiti e configurati in **componenti condivisi** in Generatore di topologie.

## <a name="see-also"></a>Vedere anche

[Panoramica del trunking SIP](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[Opzioni di distribuzione di gateway PSTN](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)
