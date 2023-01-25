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
description: Questo articolo descrive le novità di Direct Routing. Ricontrollare spesso per verificare la disponibilità di aggiornamenti.
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.collection:
- M365-voice
ms.openlocfilehash: 87befd2ff63fc5e3f0aa9e1c715972e5061b8fc7
ms.sourcegitcommit: e09591a0df9848b50bfeda29650e91e9d35724af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2023
ms.locfileid: "69981871"
---
# <a name="whats-new-for-direct-routing"></a>Novità per il routing diretto

Questo articolo descrive le novità di Direct Routing. Ricontrollare spesso per verificare la disponibilità di aggiornamenti.

## <a name="new-direct-routing-sip-endpoints"></a>Nuovi endpoint SIP routing diretto 

Microsoft introdurrà nuovi IP di segnalazione agli endpoint SIP routing diretto di Teams. Per assicurarsi che questa modifica non influirà sulla disponibilità del servizio, verificare che il controller dei confini della sessione e il firewall siano configurati per l'uso delle subnet consigliate 52.112.0.0/14 e 52.120.0.0/14 per le regole di classificazione e ACL. Per altre informazioni, vedere [Ambienti Microsoft 365, Office 365 e Office 365 GCC](direct-routing-plan.md#microsoft-365-office-365-and-office-365-gcc-environments).  

## <a name="trunk-demoting-logic-based-on-sip-options"></a>Logica di abbassare di livello trunk in base alle opzioni SIP

Viene introdotta una nuova funzionalità basata su Opzioni SIP per l'integrità del trunk. Se abilitata nella configurazione del gateway (vedere il cmdlet Set-CsOnlinePSTNGateway e il parametro SendSipOptions), la logica di routing per le chiamate in uscita abbassa di livello i trunk che non inviano periodicamente le opzioni SIP (il periodo previsto è un'opzione SIP inviata da SBC al minuto) al back-end Microsoft. Questi trunk abbassati di livello vengono inseriti alla fine dell'elenco dei trunk disponibili per la chiamata in uscita e vengono provati come gli ultimi; riducendo potenzialmente il tempo di impostazione delle chiamate.
Tutti i trunk abilitati per tale funzionalità che non inviano almeno un'opzione SIP entro cinque minuti a uno dei proxy SIP microsoft internazionali (NOAM, EMEA, APAC, OCEA) vengono considerati abbassati di livello. Se un trunk invia Opzioni SIP solo a un sottoinsieme di proxy SIP locali Microsoft, queste route vengono provate per prime e le altre vengono abbassate di livello.


## <a name="sip-support"></a>Supporto SIP

Il 1° giugno 2022 Microsoft rimuoverà il supporto per sip-all.pstnhub.microsoft.com e gli FQDN sip-all.pstnhub.gov.teams.microsoft.us dalla configurazione del routing diretto.

Se non vengono eseguite azioni prima del 1° giugno, gli utenti non saranno in grado di effettuare o ricevere chiamate tramite routing diretto.

Per evitare l'impatto del servizio:

- Usare le subnet consigliate: (52.112.0.0/14 e 52.122.0.0/15) per qualsiasi classificazione o regola ACL.
- Interrompere l'uso dell'FQDN sip-all quando si configurano i controlli bordo della sessione per il routing diretto.

Per altre informazioni, vedere [Pianificare il routing diretto](direct-routing-plan.md).

## <a name="tls-certificates"></a>Certificati TLS

Microsoft 365 sta aggiornando Teams e altri servizi per utilizzare un diverso set di autorità di certificazione radice.

Per altre informazioni e un elenco completo dei servizi interessati, vedere [Modifiche ai certificati TLS ai servizi Microsoft 365, incluso Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/tls-certificate-changes-to-microsoft-365-services-including/ba-p/3249676).

## <a name="certificate-authorities"></a>Autorità di certificazione

A partire dal 1° febbraio 2022, l'interfaccia SIP direct routing considererà attendibili solo i certificati firmati da autorità di certificazione (CA) che fanno parte del programma Microsoft Trusted Root Certificate Program. Esegui i passaggi seguenti per evitare l'impatto del servizio:

- Verificare che il certificato SBC sia firmato da una CA che fa parte del programma Microsoft Trusted Root Certificate.
- Verificare che l'estensione Utilizzo chiave estesa (EKU) del certificato includa "Autenticazione server".

Per altre informazioni sul programma Microsoft Trusted Root Certificate, vedere [Requisiti del programma - Microsoft Trusted Root Program](/security/trusted-root/program-requirements).

Per un elenco di CA attendibili, vedere [Elenco di certificati CA inclusi da Microsoft](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT).

## <a name="replace-headers"></a>Sostituire le intestazioni

A partire da aprile 2022, Direct Routing rifiuterà le richieste SIP con le intestazioni Sostituisci definite. Non ci sono modifiche ai flussi in cui Microsoft invia l'intestazione Sostituisci al session border controller (SBC).

Controllare le configurazioni SBC e assicurarsi di non usare le intestazioni Sostituisci nelle richieste SIP.

## <a name="tls10-and-11"></a>TLS1.0 e 1.1

Per fornire la crittografia migliore della categoria ai clienti, Microsoft prevede di deprecare le versioni TLS (Transport Layer Security) 1.0 e 1.1. Il 3 aprile 2022 Microsoft forza l'uso di TLS1.2 per l'interfaccia SIP routing diretto.

Per evitare qualsiasi impatto sul servizio, assicurarsi che gli SBC siano configurati per supportare TLS1.2 e possano connettersi usando uno dei pacchetti di crittografia seguenti:

- TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 ad esempio ECDHE-RSA-AES256-GCM-SHA384
- TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 ad esempio ECDHE-RSA-AES128-GCM-SHA256
- TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 ad esempio ECDHE-RSA-AES256-SHA384
- TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 ad esempio ECDHE-RSA-AES128-SHA256

## <a name="related-topics"></a>Argomenti correlati

- [Direct Routing - Protocollo SIP](direct-routing-protocols-sip.md)
