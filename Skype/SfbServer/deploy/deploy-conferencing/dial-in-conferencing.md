---
title: Configurare le conferenze telefoniche con accesso esterno in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 38d9f168-80b8-46f2-a1c0-becd84e58e73
description: 'Riepilogo: leggere questo argomento per informazioni su come configurare le conferenze telefoniche con accesso esterno in Skype for Business Server.'
ms.openlocfilehash: 92c282c87576e3d46353dabd8235521fe0097c11
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820726"
---
# <a name="configure-dial-in-conferencing-in-skype-for-business-server"></a>Configurare le conferenze telefoniche con accesso esterno in Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per informazioni su come configurare le conferenze telefoniche con accesso esterno in Skype for Business Server.
  
Dopo aver creato una topologia che include il carico di lavoro delle conferenze e le conferenze telefoniche con accesso esterno selezionate, è necessario eseguire ulteriori passaggi per configurare le conferenze telefoniche con accesso esterno. Prima di leggere questo argomento, leggere Plan [for dial-in conferencing in Skype for Business Server,](../../plan-your-deployment/conferencing/dial-in-conferencing.md) [Hardware and software requirements for conferencing in Skype for Business Server,](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md)and the Deployment flowchart and [checklist for dial-in conferencing.](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing) 
  
Per configurare le conferenze telefoniche con accesso esterno, è necessario eseguire le attività seguenti:
  
- [Configurare i dial plan](dial-in-conferencing.md#BKMK_ConfigureDialPlans)
    
- [Configurare le aree di conferenza telefonica con accesso esterno](dial-in-conferencing.md#BKMK_ConfigureDialInRegions)
    
- [Configurare i numeri di accesso esterno](dial-in-conferencing.md#BKMK_ConfigureDialInAccessNumbers)
    
- [Configurare i criteri di conferenza](dial-in-conferencing.md#BKMK_ConfigureConferencingPolicies)
    
- [Assegnare un URI linea a un account utente](dial-in-conferencing.md#BKMK_AssignaLineURI)
    
È inoltre possibile eseguire le attività facoltative seguenti. Per ulteriori informazioni su queste attività facoltative, vedere [Gestire le conferenze telefoniche con accesso esterno in Skype for Business Server.](../../manage/conferencing/dial-in-conferencing.md)
  
- Gestire i criteri PIN per le conferenze telefoniche con accesso esterno
    
- Gestire il mapping dei tasti per i comandi DTMF
    
- Creare directory conferenze
    
- Gestire gli annunci di partecipazione e di lasciare una conferenza
    
- Testare le impostazioni delle conferenze telefoniche con accesso esterno
    
- Inviare messaggi di benvenuto agli utenti con accesso remoto
    
## <a name="configure-dial-plans"></a>Configurare i dial plan
<a name="BKMK_ConfigureDialPlans"> </a>

Quando si distribuiscono le conferenze telefoniche con accesso esterno, è necessario creare o modificare uno o più dial plan per il routing dei numeri di telefono di accesso esterno. È inoltre necessario verificare che ogni dial plan contenga almeno una regola di normalizzazione, una regola che converte gli interni telefonici in numeri di telefono completi in formato E.164. 
  
Gli utenti delle conferenze telefoniche con accesso esterno aderiscono alle conferenze come utenti aziendali autenticati immettendo il pin e il numero di telefono. È necessaria una regola di normalizzazione per convertire gli interni in numeri di telefono completi in modo che gli utenti possano essere autenticati quando immettono solo un interno telefonico.
  
Per configurare i dial plan per le conferenze telefoniche con accesso esterno:
  
- Indipendentemente dal fatto che si distribuisca VoIP aziendale, modificare il dial plan globale per aggiungere un'area di conferenza telefonica con accesso esterno e per assicurarsi che una regola di normalizzazione converta in modo accurato i numeri di accesso esterno. Per istruzioni dettagliate, vedere [Creare o modificare un dial plan in Skype for Business Server.](../../deploy/deploy-enterprise-voice/dial-plans.md)
    
- Se non è stato distribuito VoIP aziendale, creare dial plan per i numeri di accesso alle conferenze telefoniche con accesso esterno. Assicurarsi di includere un'area di conferenza telefonica con accesso esterno. Per istruzioni dettagliate, vedere [Creare o modificare un dial plan in Skype for Business Server.](../../deploy/deploy-enterprise-voice/dial-plans.md)
    
- Se sono stati distribuiti VoIP aziendale, modificare VoIP aziendale dial plan in base alle esigenze per includere le aree geografiche e utilizzare le regole di normalizzazione appropriate per i numeri di accesso esterno. È inoltre possibile creare dial plan dedicati utilizzati solo per i numeri di accesso esterno. Per istruzioni dettagliate, vedere [Creare o modificare un dial plan in Skype for Business Server.](../../deploy/deploy-enterprise-voice/dial-plans.md)
    
Per informazioni dettagliate sulla creazione di regole di normalizzazione, vedere Creare o modificare una regola [di normalizzazione in Skype for Business.](../../deploy/deploy-enterprise-voice/normalization-rules.md)
  
## <a name="configure-dial-in-conferencing-regions"></a>Configurare le aree di conferenza telefonica con accesso esterno
<a name="BKMK_ConfigureDialInRegions"> </a>

Quando si imposta un dial plan, si specifica l'area per conferenze telefoniche con accesso esterno applicabile. L'area di conferenza telefonica con accesso esterno associa i numeri di accesso per le conferenze telefoniche con accesso esterno al dial plan appropriato. Quando si crea il numero di accesso remoto, si selezionano le aree geografiche che associano il numero di accesso ai dial plan appropriati. 
  
Poiché è importante specificare un'area per tutti i dial plan, è consigliabile verificare che tutti i dial plan siano aree di conferenza. 
  
Per verificare se l'area è impostata per tutti i dial plan di conferenza telefonica con accesso esterno, utilizzare il cmdlet **Get-CsDialPlan.** Se l'area non è inclusa nei dial plan, è possibile utilizzare il cmdlet **Set-CsDialPlan** per impostarla. Puoi anche usare il Pannello di controllo di Skype for Business Server per aggiornare l'area geografica nei dial plan esistenti. Per informazioni dettagliate sull'uso del Pannello di controllo di Skype for Business Server, vedere Creare o modificare [un dial plan in Skype for Business Server.](../../deploy/deploy-enterprise-voice/dial-plans.md)
  
### <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a>Per verificare se nei dial plan è impostata la proprietà relativa all'area

1. Eseguire l'accesso al computer come membro del gruppo RTCUniversalServerAdmins oppure del ruolo **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** o **CsAdministrator**.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**
    
3. Al prompt dei comandi eseguire il comando seguente:
    
   ```powershell
   Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
   ```

   Ad esempio:
    
   ```powershell
   Get-CsDialPlan
   ```

   In questo esempio vengono restituiti tutti i dial plan configurati per l'organizzazione.
    
4. Esaminare i dial plan restituiti per identificare eventualmente quelli che non includono l'area di conferenza telefonica con accesso esterno. 
    
Per ulteriori informazioni, vedere [Get-CsDialPlan.](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps)
  
### <a name="to-set-the-region-property-for-a-dial-plan"></a>Per impostare la proprietà relativa all'area per un dial plan

1. Eseguire l'accesso al computer come membro del gruppo RTCUniversalServerAdmins oppure del ruolo **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** o **CsAdministrator**.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**
    
3. Per gli eventuali dial plan che non includono l'area di conferenza telefonica con accesso esterno, eseguire:
    
   ```powershell
   Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
   ```

   Ad esempio:
    
   ```powershell
   Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
   ```

   In questo esempio il dial plan con Identity Redmond viene modificato per impostare la proprietà DialinConferencingRegion su "US West Coast". 
    
Per ulteriori informazioni, vedere [Set-CsDialPlan.](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps)
  
## <a name="configure-dial-in-access-numbers"></a>Configurare i numeri di accesso esterno
<a name="BKMK_ConfigureDialInAccessNumbers"> </a>

Quando si distribuiscono conferenze telefoniche con accesso esterno, è necessario configurare numeri di telefono che gli utenti possono comporre dalla rete PSTN (Public Switched Telephone Network) per partecipare alla parte audio delle conferenze. Questi numeri di accesso esterno vengono visualizzati negli inviti alle riunioni e nella pagina Web Impostazioni conferenza telefonica con accesso esterno.
  
Prima di creare numeri di accesso esterno, è necessario pianificare le aree di conferenza telefonica con accesso esterno e quindi configurare i dial plan con le aree. Per informazioni dettagliate sulle aree geografiche, vedere [Pianificare le conferenze telefoniche con accesso esterno in Skype for Business Server.](../../plan-your-deployment/conferencing/dial-in-conferencing.md) Per informazioni dettagliate sulla configurazione dei dial plan per le conferenze telefoniche con accesso esterno, vedere Creare o modificare [un dial plan in Skype for Business Server.](../../deploy/deploy-enterprise-voice/dial-plans.md)
  
> [!NOTE]
> Non è possibile utilizzare un nuovo numero di accesso esterno fino al completamento della replica di Servizi di dominio Active Directory di tale numero di accesso. Il completamento della replica può richiedere diverse ore. 
  
> [!NOTE]
> Dopo aver creato i numeri di accesso esterno, è possibile modificare il nome visualizzato per gli oggetti contatto di Active Directory in modo che gli utenti possano identificare più facilmente il numero di accesso corretto. Per modificare il nome visualizzato, utilizzare il cmdlet [Set-CsDialInConferencingAccessNumber.](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) Non modificare manualmente gli oggetti di Active Directory.
  
### <a name="to-create-a-dial-in-access-number"></a>Per creare un numero di accesso remoto

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Aprire il Pannello di controllo di Skype for Business Server.
    
3. Nella barra di spostamento sinistra fare clic su **Servizio di conferenza** e quindi su **Numero di accesso esterno**.
    
4. Nella pagina **Numero di accesso esterno** eseguire una delle operazioni seguenti:
    
   - Fare clic su **Nuovo** per aprire **Nuovo numero di accesso esterno**.
    
   - Fare clic su uno dei numeri di accesso esterno nell'elenco, fare clic su **Modifica** e quindi su **Mostra dettagli**.
    
     > [!NOTE]
     > Se si utilizza il campo di ricerca per cercare il contenuto di una colonna nell'elenco dei numeri di accesso esterno, i risultati ottenuti potrebbero non essere quelli previsti. Ordinare invece l'elenco in base alla colonna a cui si è interessati per identificare il numero di accesso esterno da visualizzare o modificare. 
  
5. In **Numero visualizzato** digitare il numero di telefono che gli utenti della rete PSTN (Public Switched Telephone Network) devono comporre per partecipare a una conferenza. Questo numero viene visualizzato negli inviti alle riunioni e nella pagina Web Impostazioni conferenza telefonica con accesso esterno.
    
6. In **Nome visualizzato** digitare una descrizione per il numero di accesso esterno. Questo è il nome associato al numero di accesso remoto nei risultati della ricerca di Skype for Business. Questo nome viene visualizzato nel client quando un utente chiama il numero di accesso. 
    
7. In **URI linea** digitare il numero E.164 del numero di accesso esterno nel formato URI TEL, preceduto dal simbolo + e senza utilizzare spazi. Ad esempio, tel:+14255550200.
    
    > [!NOTE]
    > Non è possibile riutilizzare lo stesso URI linea per un altro numero di accesso per conferenze con accesso esterno. 
  
8. In **URI SIP** eseguire le operazioni seguenti:
    
   - Nella casella di testo digitare un URI SIP univoco per il numero di accesso per conferenze con accesso esterno. Questo URI SIP viene visualizzato in varie posizioni, tra cui, ad esempio, i messaggi di notifica delle chiamate e le versioni precedenti dei client Lync.
    
     > [!NOTE]
     > Non è possibile riutilizzare lo stesso URI SIP per un altro numero di accesso per conferenze con accesso esterno. L'URI SIP non può essere modificato dopo che il numero di accesso è stato creato. L'unico modo per modificare l'URI SIP è quello di eliminare e ricreare il numero di accesso. 
  
   - Nella casella di riepilogo a discesa fare clic sul dominio dell'applicazione Operatore Conferenza che supporta questo numero di accesso esterno.
    
9. In **Pool** fare clic sul pool che esegue l'istanza di Operatore Conferenza che supporta il numero di accesso esterno.
    
    > [!NOTE]
    > Se è necessario modificare il pool dopo avere creato il numero di accesso, utilizzare il cmdlet [Move-CsApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) oppure eliminare e ricreare il numero di accesso.
  
10. In **Lingua principale** fare clic sulla lingua in cui verranno riprodotte le richieste per il numero di accesso esterno. 
    
    La lingua principale è la lingua utilizzata da Operatore Conferenza per rispondere alla chiamata. Le lingue supportate vengono visualizzate insieme a ogni numero di telefono di accesso nella pagina Web Impostazioni conferenza telefonica con accesso esterno.
    
11. (Facoltativo) In **Lingue secondarie (massimo quattro)** fare clic su **Aggiungi**, selezionare una o più lingue aggiuntive che si desidera supportare per i chiamanti al numero di accesso esterno e quindi fare clic su **OK**. 
    
    È possibile selezionare fino a quattro lingue secondarie per ogni numero di accesso esterno. Gli utenti possono selezionare una lingua secondaria prima di immettere l'ID conferenza quando chiamano per partecipare a una conferenza.
    
12. Per aggiungere un'area per il numero di accesso remoto, in Aree associate fare clic su **Aggiungi,** fare clic su una o più aree associate ai dial plan per il numero di accesso remoto e quindi fare clic su **OK.**
    
13. Per eliminare un'area dal numero di accesso esterno, in **Aree associate** fare clic sull'area desiderata e quindi su **Rimuovi**.
    
14. Fare clic su **Commit**.
    
## <a name="configure-conferencing-policies"></a>Configurare i criteri di conferenza
<a name="BKMK_ConfigureConferencingPolicies"> </a>

I criteri conferenza sono un'impostazione dell'account utente che specifica l'esperienza di conferenza per i partecipanti. È possibile creare criteri conferenza con ambito sito o utente. Le impostazioni dei criteri di conferenza comprendono molti aspetti della pianificazione e della partecipazione delle conferenze. Diverse impostazioni dei criteri di conferenza supportano le conferenze telefoniche con accesso esterno per i partecipanti. Quando si configurano le conferenze telefoniche con accesso esterno, è necessario verificare che questi campi siano impostati in modo appropriato per l'organizzazione e modificarli in base alle esigenze. 
  
Per ulteriori informazioni sulla configurazione dei criteri di conferenza, vedere [Gestire i criteri di conferenza in Skype for Business Server.](../../manage/conferencing/conferencing-policies.md)
  
## <a name="assign-a-line-uri-to-a-user-account"></a>Assegnare un URI linea a un account utente
<a name="BKMK_AssignaLineURI"> </a>

Gli utenti connessi tramite chiamata in ingresso immettono il proprio numero di telefono o interno e un PIN per partecipare alle conferenze come utenti autenticati. **L'URI linea telefonica** specificato per gli account utente di Skype for Business Server è necessario per l'autenticazione.
  
Nella procedura illustrata in questo argomento viene descritto come assegnare un **URI linea** per un singolo account utente. Se è necessario assegnare un **URI linea** per più account utente, è possibile creare uno script che utilizzi il cmdlet **Set-CsUser**. Per informazioni dettagliate sull'uso di uno script di esempio per assegnare **l'URI** linea a più account utente, vedere Assegnare URI [di riga a più utenti.](https://go.microsoft.com/fwlink/p/?linkId=196945)
  
1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo **Cs-UserAdministrator** o **CsAdministrator**.
    
2.  Aprire il Pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su **Utenti**.
    
4. Nel campo di ricerca digitare il nome dell'utente che si desidera configurare per le conferenze telefoniche con accesso esterno oppure fare clic su **Aggiungi filtro** per specificare i campi di ricerca e quindi fare clic su **Trova**.
    
5. Fare doppio clic sul nome utente per aprire la **finestra di dialogo Modifica utente di Skype for Business Server.**
    
6. In **Telefonia**, nel campo **URI linea** digitare un numero di telefono normalizzato univoco, ad esempio tel:+14255550200).
    
    > [!NOTE]
    > Puoi specificare **l'URI** di linea solo se Telefonia è impostata solo su **PC-to-PC,** **VoIP aziendale,** **controllo** delle chiamate remote o controllo **delle chiamate remote.**  
  
7. Fare clic su **Commit**.
    

