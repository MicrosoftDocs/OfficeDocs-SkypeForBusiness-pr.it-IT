---
title: Distribuire l'archiviazione per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50fa535c-7347-4e33-80a3-296748ef6666
description: "Riepilogo: leggere questo argomento per informazioni su come distribuire l'archiviazione per Skype for Business Server."
ms.openlocfilehash: c4f0e28c0b48cc93f1c03296f6d00555d1a7d327
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41769118"
---
# <a name="deploy-archiving-for-skype-for-business-server"></a>Distribuire l'archiviazione per Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per informazioni su come distribuire l'archiviazione per Skype for Business Server.
  
L'archiviazione viene automaticamente installata in ogni server front-end della distribuzione di Skype for Business Server, ma è comunque necessario eseguire la procedura iniziale di configurazione e la prima possibile per usarla. Prima di iniziare, assicurati di avere familiarità con i concetti in [piano per l'archiviazione in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).
  
## <a name="deployment-checklist"></a>Elenco di controllo della distribuzione

La modalità di configurazione dell'archiviazione dipende dall'opzione di archiviazione scelta: 
  
- Se si usa l'integrazione di Microsoft Exchange per tutti gli utenti della distribuzione, non è necessario configurare i criteri di archiviazione di Skype for Business Server per gli utenti. Puoi invece configurare i criteri di blocco sul posto di Exchange per supportare l'archiviazione per gli utenti ospitati in Exchange, con le cassette postali inserite sul posto. Per informazioni dettagliate sulla configurazione di questi criteri, vedere la documentazione del prodotto Exchange.
    
- Se non si usa l'integrazione di Microsoft Exchange per tutti gli utenti della distribuzione, è necessario aggiungere i database di archiviazione di Skype for Business Server (database di SQL Server) alla topologia, pubblicare la topologia aggiornata e quindi configurare i criteri di archiviazione e impostazioni per gli utenti. È possibile distribuire i database di archiviazione contemporaneamente alla distribuzione della topologia iniziale o dopo avere distribuito almeno un pool di front-end o un server Standard Edition. Questo documento descrive come distribuire i database di archiviazione aggiungendoli a una distribuzione esistente.
    
Se si Abilita l'archiviazione in un pool Front-end o in un server Standard Edition, è consigliabile abilitarlo per tutti gli altri pool Front end e i server Standard Edition nella distribuzione. Il motivo è che gli utenti le cui comunicazioni devono essere archiviati possono essere invitati a una conversazione di messaggistica istantanea di gruppo o a riunioni ospitate in un pool diverso. Se l'archiviazione non è abilitata nel pool in cui è ospitata la conversazione o la riunione, la sessione completa potrebbe non essere archiviata. In questi casi, è ancora possibile archiviare messaggi istantanei con utenti abilitati all'archiviazione, ma non per i file di contenuto di conferenza e gli eventi di conferenza o di uscita.
  
> [!IMPORTANT]
> Se l'archiviazione è fondamentale per i motivi di conformità dell'organizzazione, assicurarsi di distribuire l'archiviazione, configurare i criteri e altre opzioni a livello appropriato e quindi attivare l'archiviazione per tutti gli utenti appropriati, prima di abilitare gli utenti per Skype for Business Server. 
  
La tabella seguente offre una panoramica dei passaggi necessari per distribuire l'archiviazione in una topologia esistente.
  
|**Fase**|**Passaggi**|**Ruoli e appartenenze ai gruppi**|**Documentazione**|
|:-----|:-----|:-----|:-----|
|**Installare hardware e software prerequisiti** <br/> |Per usare l'integrazione di Microsoft Exchange (usando Exchange per archiviare l'archiviazione per alcuni o tutti gli utenti), è necessaria una distribuzione di Exchange esistente.  <br/> Per usare database di archiviazione distinti (tramite database di SQL Server) per l'archiviazione dello spazio di archiviazione per alcuni o tutti gli utenti, SQL Server nel server in cui verranno archiviati i dati di archiviazione.  <br/> L'archiviazione viene eseguita nei server front-end di un pool Enterprise e di server Standard Edition. Non ha requisiti hardware o software aggiuntivi oltre a ciò che è necessario per installare tali server.  <br/> |Utente del dominio che è un membro del gruppo Administrators locale.  <br/> |[Requisiti server di Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Requisiti ambientali di Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/>  [Pianificare l'integrazione di Skype for Business ed Exchange](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md) <br/>[Requisiti di sistema per Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md) |
|**Creare la topologia interna appropriata per supportare l'archiviazione (solo se non si usa l'integrazione di Microsoft Exchange per tutti gli utenti della distribuzione)** <br/> |Eseguire Generatore di topologia per aggiungere database di archiviazione di Skype for Business Server (database di SQL Server) alla topologia e quindi pubblicare la topologia.  <br/> |Per definire una topologia per incorporare i database di archiviazione, un account membro del gruppo utenti locali.  <br/> Per pubblicare la topologia, un account che sia un membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins e che disponga delle autorizzazioni di controllo completo (lettura/scrittura/modifica) nella condivisione file da usare per il file Store di Skype for Business Server (in modo che il generatore di topologia possa configurare gli elenchi DACL necessari).  <br/> |[Aggiungere database di archiviazione a una distribuzione esistente in Skype for Business Server](add-archiving-databases.md) <br/> |
|**Configurare l'autenticazione da server a server (solo se si usa l'integrazione di Microsoft Exchange)** <br/> |Configurare i server per consentire l'autenticazione tra Skype for Business Server ed Exchange. È consigliabile eseguire **test-CsExchangeStorageConnectivity testuser_sipUri-dumpster della cartella** per convalidare la connettività di archiviazione dell'archiviazione di Exchange prima di abilitare l'archiviazione. <br/> |Un account con le autorizzazioni appropriate per la gestione dei certificati nei server.  <br/> |Gestire l'autenticazione da server a server  <br/> |
|**Configurare le opzioni di archiviazione e i criteri** <br/> |Configurare l'archiviazione, ad esempio se usare l'integrazione di Microsoft Exchange, i criteri globali e tutti i criteri per i siti e gli utenti (quando non si usa l'integrazione di Microsoft Exchange per tutti gli archivi dati) e le opzioni di archiviazione specifiche, come la modalità critica e i dati esportare ed eliminare.  <br/> Se si usa l'integrazione di Microsoft Exchange, configurare i criteri di blocco sul posto di Exchange in base alle esigenze.  <br/> |Gruppo RTCUniversalServerAdmins (solo Windows PowerShell) o assegna agli utenti il ruolo CSArchivingAdministrator o CSAdministrator.  <br/> |[Configurare le opzioni di archiviazione per Skype for Business Server](configure-archiving-options.md) <br/> Documentazione del prodotto Exchange (se si usa l'integrazione di Microsoft Exchange).  <br/> |
   

