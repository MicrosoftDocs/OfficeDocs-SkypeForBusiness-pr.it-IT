---
title: Configurare i criteri di archiviazione per Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: 'Riepilogo: leggere questo argomento per informazioni su come configurare i criteri di archiviazione iniziali per Skype for Business Server utenti.'
ms.openlocfilehash: 62e61d951c7e05effa68afd13c849c027b40a896
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60749525"
---
# <a name="configure-archiving-policies-for-skype-for-business-server"></a>Configurare i criteri di archiviazione per Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per informazioni su come configurare i criteri di archiviazione iniziali per Skype for Business Server utenti.
  
In Skype for Business Server vengono utilizzati i criteri per abilitare e disabilitare l'archiviazione per le comunicazioni interne e esterne per gli utenti ospitati in Skype for Business Server. Sono incluse le attività seguenti:
  
- Criteri globali creati per impostazione predefinita quando si distribuisce Skype for Business Server
    
- Criteri facoltativi a livello di sito che specificano la modalità di implementazione dell'archiviazione per un sito specifico
    
- Criteri facoltativi a livello di utente che specificano la modalità di implementazione dell'archiviazione per utenti specifici
    
I criteri di archiviazione vengono inizialmente impostati quando si distribuisce l'archiviazione, ma è possibile modificare, aggiungere ed eliminare i criteri dopo la distribuzione. Nel Skype for Business Server di controllo è possibile  utilizzare la pagina  Criteri di archiviazione del gruppo Archiviazione e monitoraggio per gestire i criteri a livello globale, di sito e di utente.
  
> [!NOTE]
> Per controllare l'implementazione dell'archiviazione, è necessario specificare opzioni, ad esempio se archiviare la messaggistica istantanea o le conferenze, l'uso della modalità critica e le opzioni di eliminazione. Per impostazione predefinita, nella configurazione di archiviazione globale o in qualsiasi configurazione di archiviazione del sito o del pool non sono abilitate opzioni. È consigliabile specificare tutte le opzioni appropriate prima di abilitare l'archiviazione per le comunicazioni interne o esterne. Per informazioni dettagliate, vedere [Configure archiving options for Skype for Business Server](configure-archiving-options.md). 
  
> [!NOTE]
> Se si abilita l'integrazione di Microsoft Exchange per la distribuzione, i criteri di blocco del Exchange In-Place controllano se l'archiviazione è abilitata per gli utenti ospitati in Exchange e che le cassette postali vengono In-Place conservazione. 
  
Per informazioni dettagliate sul funzionamento dei criteri di archiviazione, inclusa la gerarchia dei criteri globali, dei siti e degli utenti, vedere [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md). Per informazioni dettagliate su come gestire i criteri dopo la distribuzione, vedere [Manage archiving policies in Skype for Business Server](../../manage/archiving/policies.md).
  
## <a name="global-policy"></a>Criterio globale

Quando si distribuiscono i Front End Server, Skype for Business Server un criterio globale per l'archiviazione. Per impostazione predefinita, l'archiviazione è disabilitata nei criteri globali. Il criterio globale controlla se l'archiviazione è abilitata per le comunicazioni interne ed esterne per l'intera distribuzione, a meno che non vengano impostati criteri sito o utente, che sostituiscono i criteri globali o se si utilizza l'integrazione di Microsoft Exchange per alcuni o tutti gli utenti. Se si utilizza l'integrazione di Microsoft Exchange, il criterio globale non si applica agli utenti ospitati in Exchange e le cassette postali vengono In-Place blocco.
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a>Configurare i criteri globali per l'archiviazione per Skype for Business Server database di archiviazione

1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo. 
    
3. Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Criteri di archiviazione**.
    
4. Nella pagina **Criteri di archiviazione** fare clic su **Globale**, **Modifica** e quindi su **Mostra dettagli**.
    
5. In **Modifica Criteri di archiviazione - Globale** eseguire le operazioni seguenti:
    
   - In **Nome**, se non si vuole usare il nome predefinito Globale, specificare un nuovo nome per i criteri globali. 
    
   - In **Descrizione** fornire informazioni sul criterio, ad esempio Criteri globali per *divisionName.*
    
   - Per controllare l'archiviazione delle comunicazioni interne per tutti i siti e gli utenti non controllati in modo specifico tramite criteri utente o sito, selezionare o deselezionare la casella di controllo **Archivia comunicazioni interne**.
    
   - Per controllare l'archiviazione delle comunicazioni esterne per tutti i siti e gli utenti non controllati in modo specifico tramite criteri utente o di sito, selezionare o deselezionare la casella di controllo **Archivia comunicazioni esterne**.
    
6. Fare clic su **Commit**.
    
## <a name="site-policies"></a>Criteri sito

È possibile abilitare o disabilitare l'archiviazione per siti specifici creando un criterio di archiviazione per ognuno di tali siti. I criteri sito hanno la precedenza sul criterio globale, mentre i criteri utente hanno la precedenza su criteri sito. I criteri di archiviazione si applicano solo se non si utilizza l'integrazione di Microsoft Exchange o, se si utilizza l'integrazione di Microsoft Exchange, ma si dispone di alcuni utenti che non sono ospitati in Exchange e hanno le loro cassette postali messe In-Place conservazione.
  
### <a name="create-an-archiving-policy-for-a-site"></a>Creare criteri di archiviazione per un sito

1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo.
    
3. Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Criteri di archiviazione**.
    
    Per informazioni dettagliate sul funzionamento dei criteri di archiviazione, inclusa la gerarchia dei criteri globali, dei siti e degli utenti, vedere [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).
    
4. Fare clic su **Nuovo** e quindi su **Criteri sito**.
    
5. In **Selezionare un sito** fare clic sul sito a cui deve essere applicato il criterio.
    
6. In **Crea nuovi criteri di archiviazione** eseguire le operazioni seguenti:
    
   - In **Nome** specificare il nome per il criterio del sito. 
    
   - In **Descrizione** fornire informazioni sui criteri del sito, ad esempio criteri sito per Redmond.
    
   - Per controllare l'archiviazione delle comunicazioni interne per il sito specificato, selezionare o deselezionare la **casella di controllo** Archivia comunicazioni interne.
    
   - Per controllare l'archiviazione delle comunicazioni esterne per il sito specificato, selezionare o deselezionare la **casella di** controllo Archivia comunicazioni esterne.
    
7. Fare clic su **Commit**.
    
## <a name="user-policies"></a>Criteri utente

È possibile abilitare o disabilitare l'archiviazione per utenti specifici creando e configurando un criterio di archiviazione per gli utenti e quindi applicando il criterio a utenti o gruppi di utenti specifici. I criteri utente sostituiscono eventuali criteri globali o sito. I criteri di archiviazione si applicano solo se non si utilizza l'integrazione di Microsoft Exchange o, se si utilizza l'integrazione di Microsoft Exchange, ma si dispone di alcuni utenti che non sono ospitati in Exchange e hanno le loro cassette postali messe In-Place conservazione.
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a>Configurare un criterio di archiviazione per gli utenti ospitati in Skype for Business Server

1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo. 
    
3. Nella barra di spostamento sinistra fare clic su **Monitoraggio e archiviazione** e quindi su **Criteri di archiviazione**.
    
4. Fare clic su **Nuovo** e quindi su **Criteri utente**.
    
5. In **Nuovi criteri di archiviazione** eseguire le operazioni seguenti:
    
   - In **Nome** specificare un nome per i criteri utente. 
    
   - In **Descrizione** immettere informazioni sugli scopi dei criteri utente, ad esempio "Criteri utente per il reparto legale".
    
   - Per controllare l'archiviazione delle comunicazioni interne per i criteri utente, selezionare o deselezionare la casella di controllo **Archivia comunicazioni interne**.
    
   - Per controllare l'archiviazione delle comunicazioni esterne per i criteri utente, selezionare o deselezionare la casella di controllo **Archivia comunicazioni esterne**.
    
6. Fare clic su **Commit**.
    
I criteri utente si applicano solo agli utenti a cui vengono assegnati.
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a>Applicare un criterio Skype for Business Server di archiviazione a un utente

1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo. 
    
3. Sulla barra di spostamento sinistra fare clic su **Utenti** e quindi cercare l'account utente che si desidera configurare.
    
4. Nella tabella dei risultati di ricerca fare clic sull'account utente, fare clic su **Modifica** e quindi fare clic su **Mostra dettagli**.
    
5. In **Modifica Skype for Business Server utente** in Criteri di **archiviazione** selezionare il criterio utente di archiviazione che si desidera applicare.
    
    > [!NOTE]
    > Le **\<Automatic\>** impostazioni applicano le impostazioni di installazione predefinite del server. Queste impostazioni vengono applicate automaticamente dal server.
  
6. Fare clic su **Commit**.
    

