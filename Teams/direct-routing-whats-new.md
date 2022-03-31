---
title: Novità del routing diretto
ms.reviewer: CarolynRowe
author: wlibebe
ms.author: wlibebe
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Questo articolo descrive le novità del routing diretto. Controllare spesso la disponibilità di aggiornamenti.
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b6f2ec21ec3e7f4278443d6bcab4b4220db3619f
ms.sourcegitcommit: cbdc80c302e97d18a923ef57bb5d4b6cf7676d00
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2022
ms.locfileid: "64556740"
---
# <a name="whats-new-for-direct-routing"></a>Novità del routing diretto

Questo articolo descrive le novità del routing diretto. Controllare spesso la disponibilità di aggiornamenti.

## <a name="sip-support"></a>Supporto SIP

Il 1° giugno 2022 Microsoft rimuoverà il supporto per sip-all.pstnhub.microsoft.com e sip-all.pstnhub.gov.teams.microsoft.us fqdn dalla configurazione di Routing diretto.

Se non vengono eseguite azioni prima del 1° giugno, gli utenti non potranno effettuare o ricevere chiamate tramite routing diretto.

Per evitare l'impatto del servizio:

- Usare le subnet consigliate: (52.112.0.0/14 e 52.120.0.0/14) per qualsiasi regola di classificazione o ACL.
- Interrompere l'uso dell'FQDN sip-all durante la configurazione di Session Border Controls per il routing diretto.

Per altre informazioni, vedere [Pianificare il routing diretto](direct-routing-plan.md).

## <a name="tls-certificates"></a>Certificati TLS

Microsoft 365 sta aggiornando Teams e altri servizi in modo da usare un set diverso di Autorità di certificazione radice(CA).

Per altre informazioni e un elenco completo dei servizi interessati, vedere Modifiche ai certificati TLS per Microsoft 365 [servizi, inclusi](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/tls-certificate-changes-to-microsoft-365-services-including/ba-p/3249676) Microsoft Teams.

## <a name="certificate-authorities"></a>Autorità di certificazione

A partire dal 1° febbraio 2022, l'interfaccia SIP di routing diretto considera attendibili solo i certificati firmati da Autorità di certificazione (CA) che fanno parte del programma Microsoft Trusted Root Certificate Program. Eseguire la procedura seguente per evitare l'impatto del servizio:

- Verificare che il certificato SBC sia firmato da un'autorità di certificazione che fa parte del programma Microsoft Trusted Root Certificate Program.
- Verificare che l'estensione EKU (Extended Key Usage) del certificato includa "Autenticazione server".

Per altre informazioni sul programma Microsoft Trusted Root Certificate, vedere [Requisiti del programma - Microsoft Trusted Root Program](/security/trusted-root/program-requirements).

Per un elenco di CA attendibili, vedere [Elenco certificati CA inclusi Microsoft](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT).

## <a name="replace-headers"></a>Sostituire le intestazioni

A partire da aprile 2022, il routing diretto rifiuta le richieste SIP con intestazioni Replaces definite. Non ci sono modifiche ai flussi in cui Microsoft invia l'intestazione Replaces al Session Border Controller(SBC).

Controllare le configurazioni SBC e assicurarsi di non usare le intestazioni Replaces nelle richieste SIP.

## <a name="tls10-and-10"></a>TLS1.0 e 1.0

Per fornire la crittografia più avanzata ai clienti, Microsoft prevede di deprecazione delle versioni 1.0 e 1.1 di Transport Layer Security (TLS). Il 3 aprile 2022 Microsoft forza l'utilizzo di TLS1.2 per l'interfaccia SIP di routing diretto.

Per evitare qualsiasi impatto sul servizio, verificare che i SBC siano configurati per supportare TLS1.2 e possano connettersi usando una delle suite di crittografia seguenti:

- TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384, ad esempio ECDHE-RSA-AES256-GCM-SHA384
- TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256, ad esempio ECDHE-RSA-AES128-GCM-SHA256
- TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384, ad esempio ECDHE-RSA-AES256-SHA384
- TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256, ad esempio ECDHE-RSA-AES128-SHA256

## <a name="related-topics"></a>Argomenti correlati

- [Routing diretto - Protocollo SIP](direct-routing-protocols-sip.md)
