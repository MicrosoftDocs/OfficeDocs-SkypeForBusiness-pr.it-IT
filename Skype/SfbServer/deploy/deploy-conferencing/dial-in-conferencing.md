---
title: Configurare i servizi di conferenza telefonica con accesso esterno in Skype for Business Server
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
ms.assetid: 38d9f168-80b8-46f2-a1c0-becd84e58e73
description: 'Riepilogo: leggere questo argomento per informazioni su come configurare i servizi di conferenza telefonica con accesso esterno in Skype for Business Server.'
ms.openlocfilehash: 4e8523cbaadfc13b985cf33e06e68fcd5d209c89
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768529"
---
# <a name="configure-dial-in-conferencing-in-skype-for-business-server"></a>Configurare i servizi di conferenza telefonica con accesso esterno in Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per informazioni su come configurare i servizi di conferenza telefonica con accesso esterno in Skype for Business Server.
  
Dopo aver creato una topologia che include il carico di lavoro per le conferenze e i servizi di conferenza telefonica con accesso esterno, è necessario eseguire ulteriori operazioni per configurare le conferenze telefoniche con accesso esterno. Prima di leggere questo argomento, assicurati di aver letto [piano per i servizi di conferenza telefonica con accesso esterno in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md), [requisiti hardware e software per le conferenze in Skype for Business Server](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md)e il [diagramma di flusso e l'elenco di controllo della distribuzione per i servizi di conferenza telefonica con accesso esterno](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing). 
  
Per configurare i servizi di conferenza telefonica con accesso esterno, è necessario eseguire le attività seguenti:
  
- [Configurare i dial plan](dial-in-conferencing.md#BKMK_ConfigureDialPlans)
    
- [Configurare le aree di conferenza telefonica con accesso esterno](dial-in-conferencing.md#BKMK_ConfigureDialInRegions)
    
- [Configurare i numeri di accesso per la chiamata in ingresso](dial-in-conferencing.md#BKMK_ConfigureDialInAccessNumbers)
    
- [Configurare i criteri di conferenza](dial-in-conferencing.md#BKMK_ConfigureConferencingPolicies)
    
- [Assegnare un URI di linea a un account utente](dial-in-conferencing.md#BKMK_AssignaLineURI)
    
È inoltre possibile eseguire le attività facoltative seguenti. Per altre informazioni su queste attività facoltative, vedere gestire le conferenze telefoniche con [accesso esterno in Skype for Business Server](../../manage/conferencing/dial-in-conferencing.md).
  
- Gestire i criteri PIN per i servizi di conferenza telefonica con accesso esterno
    
- Gestire il mapping dei tasti per i comandi DTMF
    
- Creare directory conferenza
    
- Gestire gli annunci per partecipare a una conferenza e uscire
    
- Verificare le impostazioni di conferenza telefonica con accesso esterno
    
- Inviare messaggi di benvenuto agli utenti con accesso esterno
    
## <a name="configure-dial-plans"></a>Configurare i dial plan
<a name="BKMK_ConfigureDialPlans"> </a>

Quando si distribuiscono i servizi di conferenza telefonica con accesso esterno, è necessario creare o modificare uno o più piani di chiamata per il routing dei numeri di telefono di Access per le chiamate in ingresso. Devi anche verificare che ogni dial plan contenga almeno una regola di normalizzazione, una regola che converte le estensioni telefoniche in numeri di telefono completi nel formato E. 164. 
  
Gli utenti di servizi di conferenza telefonica con accesso esterno partecipano alle conferenze come utenti autenticati dell'organizzazione immettendo il PIN (Personal Identification Number) e il relativo numero di telefono. È necessaria una regola di normalizzazione per convertire le estensioni in numeri di telefono completi in modo che gli utenti possano essere autenticati quando immettono solo un'estensione telefonica.
  
Per configurare i dial plan per i servizi di conferenza telefonica con accesso esterno:
  
- Se si distribuisce o meno Enterprise Voice, modificare il dial plan globale per aggiungere un'area di conferenza telefonica con accesso esterno e verificare che una regola di normalizzazione converta accuratamente i numeri di accesso esterno. Per istruzioni dettagliate, vedere [creare o modificare un dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).
    
- Se non è stata distribuita VoIP aziendale, creare piani di chiamata per i numeri di accesso per i servizi di conferenza telefonica con chiamata in ingresso. Assicurati di includere un'area di conferenza telefonica con accesso esterno. Per istruzioni dettagliate, vedere [creare o modificare un dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).
    
- Se Enterprise Voice è stato distribuito, modificare i piani per le chiamate vocali aziendali in base alle esigenze per includere le aree geografiche e usare le regole di normalizzazione per i numeri di accesso esterno. È anche possibile creare piani di chiamata dedicati usati solo per i numeri di accesso esterno. Per istruzioni dettagliate, vedere [creare o modificare un dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).
    
Per informazioni dettagliate sulla creazione di regole di normalizzazione, vedere [creare o modificare una regola di normalizzazione in Skype for business](../../deploy/deploy-enterprise-voice/normalization-rules.md).
  
## <a name="configure-dial-in-conferencing-regions"></a>Configurare le aree di conferenza telefonica con accesso esterno
<a name="BKMK_ConfigureDialInRegions"> </a>

Quando si configura un dial plan, si specifica l'area dei servizi di conferenza telefonica con accesso esterno che si applica a tale dial plan. L'area dei servizi di conferenza telefonica con accesso esterno associa i numeri per le conferenze telefoniche con chiamata in ingresso con il dial plan appropriato. Quando si crea il numero di accesso per la chiamata in ingresso, si selezionano le aree geografiche che associano il numero di accesso con i dial plan appropriati. 
  
Poiché è importante specificare un'area geografica per tutti i dial plan, è consigliabile verificare che tutti i dial plan abbiano aree di conferenza. 
  
Per verificare se l'area è impostata per tutti i piani di conferenza telefonica con accesso esterno, usare il cmdlet **Get-CsDialPlan** . Se l'area non è presente nei dial plan, è possibile usare il cmdlet **Set-CsDialPlan** per impostare l'area geografica. Puoi anche usare il pannello di controllo di Skype for Business Server per aggiornare l'area dei dial plan esistenti. Per informazioni dettagliate sull'uso del pannello di controllo di Skype for Business Server, vedere [creare o modificare un dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).
  
### <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a>Per verificare se i dial plan hanno la proprietà Region impostata

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo **Cs-voiceadministrator**, **Cs-ServerAdministrator**o **CsAdministrator** .
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
3. Eseguire la procedura seguente al prompt dei comandi:
    
   ```powershell
   Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
   ```

   Ad esempio:
    
   ```powershell
   Get-CsDialPlan
   ```

   In questo esempio vengono restituiti tutti i dial plan configurati per l'organizzazione.
    
4. Esaminare i piani di chiamata restituiti per identificare gli elementi mancanti nell'area dei servizi di conferenza telefonica con accesso esterno. 
    
Per altre informazioni, vedere [Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps).
  
### <a name="to-set-the-region-property-for-a-dial-plan"></a>Per impostare la proprietà Region per un dial plan

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo **Cs-voiceadministrator**, **Cs-ServerAdministrator**o **CsAdministrator** .
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
3. Per gli eventuali dial plan mancanti dell'area di conferenza telefonica con accesso esterno, eseguire:
    
   ```powershell
   Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
   ```

   Ad esempio:
    
   ```powershell
   Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
   ```

   In questo esempio, il dial plan con l'identità di Redmond viene modificato per impostare la proprietà DialinConferencingRegion su "US West Coast". 
    
Per altre informazioni, vedere [Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps).
  
## <a name="configure-dial-in-access-numbers"></a>Configurare i numeri di accesso per la chiamata in ingresso
<a name="BKMK_ConfigureDialInAccessNumbers"> </a>

Quando si distribuiscono i servizi di conferenza telefonica con accesso esterno, è necessario configurare i numeri di telefono che gli utenti possono effettuare la chiamata dalla rete PSTN (Public Switched Telephone Network) per partecipare alla parte audio delle conferenze. I numeri di accesso per le connessioni in ingresso vengono visualizzati negli inviti alle riunioni e nella pagina Web delle impostazioni di conferenza telefonica con accesso esterno.
  
Prima di poter creare numeri di accesso per la chiamata in ingresso, è necessario pianificare le aree dei servizi di conferenza telefonica con accesso esterno e quindi configurare i dial plan con le aree geografiche. Per informazioni dettagliate sulle aree geografiche, vedere [pianificare i servizi di conferenza telefonica con accesso esterno in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md). Per informazioni dettagliate sulla configurazione dei dial plan per i servizi di conferenza telefonica con accesso esterno, vedere [creare o modificare un dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).
  
> [!NOTE]
> Non è possibile usare un nuovo numero di accesso esterno finché non viene completata la replica di Active Directory Domain Services (AD DS). La replica può richiedere diverse ore per il completamento. 
  
> [!NOTE]
> Dopo aver creato i numeri di accesso esterno, è possibile modificare il nome visualizzato per gli oggetti contatto di Active Directory in modo che gli utenti possano identificare più facilmente il numero di accesso corretto. Per modificare il nome visualizzato, usare il cmdlet [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) . Non è consigliabile modificare manualmente gli oggetti di Active Directory.
  
### <a name="to-create-a-dial-in-access-number"></a>Per creare un numero di accesso per la chiamata in ingresso

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
    
2. Aprire il pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su servizi di conferenza e quindi su **numero di accesso** **esterno** .
    
4. Nella pagina **numero di accesso** esterno effettuare una delle operazioni seguenti:
    
   - Fare clic su **nuovo** per aprire il **nuovo numero di accesso**esterno.
    
   - Fare clic su uno dei numeri di accesso per la chiamata in ingresso nell'elenco, fare clic su **modifica**e quindi su **Mostra dettagli**.
    
     > [!NOTE]
     > L'uso del campo di ricerca per cercare il contenuto di una colonna nell'elenco dei numeri di accesso per la chiamata in ingresso potrebbe non restituire i risultati previsti. Ordinare invece l'elenco in base alla colonna di interesse per identificare il numero di accesso esterno che si vuole visualizzare o modificare. 
  
5. In **numero di visualizzazione**Digitare il numero di telefono che gli utenti del telefono PSTN (Public Switched Telephone Network) Dial per partecipare a una conferenza. Questo numero viene visualizzato negli inviti alle riunioni e nella pagina Web delle impostazioni dei servizi di conferenza telefonica con accesso esterno.
    
6. In **nome visualizzato**Digitare una descrizione per il numero di accesso esterno. Questo è il nome associato al numero di accesso esterno nei risultati della ricerca di Skype for business. Questo nome viene visualizzato nel client quando un utente chiama il numero di accesso. 
    
7. In **URI di linea**Digitare il numero e. 164 del numero di accesso esterno in formato Tel URI, incluso il simbolo + prima del numero ed escludendo gli spazi. Ad esempio, Tel: + 14255550200.
    
    > [!NOTE]
    > Lo stesso URI di linea non può essere riutilizzato da un altro numero di accesso per i servizi di conferenza telefonica in ingresso. 
  
8. In **URI SIP**eseguire le operazioni seguenti:
    
   - Nella casella di testo digitare un URI SIP univoco per questo numero di accesso per i servizi di conferenza telefonica con chiamata in ingresso. Questo URI SIP viene visualizzato in varie posizioni, inclusi, ma non solo, i messaggi di notifica delle chiamate e le versioni precedenti dei client Lync.
    
     > [!NOTE]
     > Lo stesso URI SIP non può essere riutilizzato da un altro numero di accesso per i servizi di conferenza telefonica con chiamata in ingresso. L'URI SIP non può essere modificato dopo la creazione del numero di accesso. L'unico modo per modificare l'URI SIP consiste nell'eliminare e ricreare il numero di accesso. 
  
   - Nella casella di riepilogo a discesa fare clic sul dominio dell'applicazione operatore di conferenza che supporta questo numero di accesso esterno.
    
9. In **pool**fare clic sul pool in cui è in esecuzione l'istanza di operatore conferenza che supporta questo numero di accesso esterno.
    
    > [!NOTE]
    > Se è necessario modificare il pool dopo la creazione del numero di accesso, è necessario usare il cmdlet [Move-CsApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) oppure eliminare e ricreare il numero di accesso.
  
10. In **lingua principale**fare clic sulla lingua in cui vengono riprodotti le richieste per questo numero di accesso esterno. 
    
    La lingua principale è la lingua che l'operatore di conferenza USA per rispondere alla chiamata. Le lingue supportate vengono visualizzate accanto a ogni numero di telefono di Access nella pagina Web delle impostazioni dei servizi di conferenza telefonica con accesso esterno.
    
11. Opzionale In **lingue secondarie (massimo quattro)** fare clic su **Aggiungi**, selezionare una o più lingue aggiuntive che si desidera supportare per i chiamanti per il numero di accesso esterno e quindi fare clic su **OK**. 
    
    È possibile scegliere fino a quattro lingue secondarie per ogni numero di accesso esterno. Gli utenti possono selezionare una lingua secondaria prima di immettere l'ID conferenza quando effettuano la chiamata a una conferenza.
    
12. Per aggiungere un'area geografica per il numero di accesso esterno, fare clic su **Aggiungi**in **aree geografiche associate**, fare clic su una o più aree geografiche associate ai dial plan per questo numero di accesso esterno e quindi fare clic su **OK**.
    
13. Per eliminare un'area dal numero di accesso esterno, in **aree geografiche associate**fare clic sull'area che si vuole eliminare e quindi fare clic su **Rimuovi**.
    
14. Fare clic su **Commit**.
    
## <a name="configure-conferencing-policies"></a>Configurare i criteri di conferenza
<a name="BKMK_ConfigureConferencingPolicies"> </a>

Criteri di conferenza è un'impostazione dell'account utente che specifica l'esperienza di conferenza per i partecipanti. È possibile creare criteri di conferenza con un ambito del sito o un ambito utente. Le impostazioni dei criteri di conferenza includono molti aspetti della pianificazione e della partecipazione a conferenze. Diverse impostazioni dei criteri di conferenza supportano i servizi di conferenza telefonica con accesso esterno per i partecipanti. Quando si configurano i servizi di conferenza telefonica con accesso esterno, è necessario verificare che questi campi siano impostati in modo appropriato per l'organizzazione e modificarli in base alle esigenze. 
  
Per altre informazioni sulla configurazione dei criteri di conferenza, vedere [gestire i criteri di conferenza in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).
  
## <a name="assign-a-line-uri-to-a-user-account"></a>Assegnare un URI di linea a un account utente
<a name="BKMK_AssignaLineURI"> </a>

Gli utenti con accesso esterno immettono il loro numero di telefono o l'estensione e un PIN per partecipare alle conferenze come utenti autenticati. L'URI della **linea** di telefonia specificato negli account utente di Skype for Business Server è necessario per l'autenticazione.
  
La procedura descritta in questo argomento descrive come assegnare un **URI di linea** per un singolo account utente. Se è necessario assegnare un **URI di linea** per più account utente, è possibile creare uno script che usa il cmdlet **Set-CsUser** . Per informazioni dettagliate sull'uso di uno script di esempio per assegnare l' **URI di linea** a più account utente, vedere [assegnare URI di linea a più utenti](https://go.microsoft.com/fwlink/p/?linkId=196945).
  
1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo **CS-UserAdministrator** o **CsAdministrator** .
    
2.  Aprire il pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su **utenti**.
    
4. Nel campo di ricerca digitare il nome dell'utente che si vuole configurare per i servizi di conferenza telefonica con accesso esterno o fare clic su **Aggiungi filtro** per specificare i campi di ricerca e quindi fare clic su **trova**.
    
5. Fare doppio clic sul nome utente per aprire la finestra di dialogo **modifica utente di Skype for Business Server** .
    
6. In **telefonia**, nel campo **URI di linea** digitare un numero di telefono normalizzato univoco, ad esempio Tel: + 14255550200.
    
    > [!NOTE]
    > Puoi specificare l' **URI di linea** solo se la **telefonia** è impostata solo su **PC-to-PC**, **VoIP aziendale**, **controllo delle chiamate remote** o **controllo delle chiamate remote solo**. 
  
7. Fare clic su **Commit**.
    

