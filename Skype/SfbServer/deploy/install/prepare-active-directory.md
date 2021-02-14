---
title: Preparare Active Directory per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985077a4-c8e1-4d5a-9fcf-fef41cf6d61d
description: "Riepilogo: informazioni su come preparare il dominio di Active Directory per un'installazione di Skype for Business Server. Scaricare una versione di valutazione gratuita di Skype for Business Server dal Centro di valutazione Microsoft all'indirizzo: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server ."
ms.openlocfilehash: 6196855ffeaf33fbea11c47d56c620e3df9195ee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801676"
---
# <a name="prepare-active-directory-for-skype-for-business-server"></a>Preparare Active Directory per Skype for Business Server
 
**Riepilogo:** Informazioni su come preparare il dominio di Active Directory per un'installazione di Skype for Business Server. Scaricare una versione di valutazione gratuita di Skype for Business Server dal [Microsoft Evaluation Center.](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)
  
Skype for Business Server funziona a stretto contatto con Active Directory. È necessario preparare il dominio di Active Directory per l'utilizzo con Skype for Business Server. Questo processo viene eseguito nella Distribuzione guidata e viene eseguito una sola volta per il dominio. Questo perché il processo crea gruppi e modifica il dominio ed è necessario farlo una sola volta. È possibile eseguire i passaggi da 1 a 5 in qualsiasi ordine. È tuttavia necessario eseguire i passaggi 6, 7 e 8 nell'ordine e dopo i passaggi da 1 a 5, come illustrato nel diagramma. La preparazione di Active Directory è il passaggio 4 di 8. Per ulteriori informazioni sulla pianificazione di Active Directory, vedere Requisiti ambientali per [Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o Requisiti server per Skype for Business Server [2019.](../../../SfBServer2019/plan/system-requirements.md)
  
![diagramma di panoramica](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a>Preparazione di Active Directory

Skype for Business Server è strettamente integrato con Servizi di dominio Active Directory. Prima di poter installare Skype for Business Server per la prima volta, è necessario preparare Active Directory. La sezione della Distribuzione guidata intitolata **Preparare Active Directory** prepara l'ambiente Active Directory per l'utilizzo con Skype for Business Server.
  
> [!NOTE]
> Skype for Business Server usa Servizi di dominio Active Directory per tenere traccia e comunicare con tutti i server di una topologia. La maggior parte di questi server deve essere aggiunto al dominio in modo che Skype for Business Server possa funzionare correttamente. Tenere presente che i server come Edge e Proxy inverso non devono essere aggiunti a un dominio.
  
> [!IMPORTANT]
> La procedura di preparazione di Active Directory deve essere eseguita una sola volta per ogni dominio della distribuzione. 
  
Guardare i passaggi video per **preparare Active Directory:**
  
> [!video https://www.microsoft.com/videoplayer/embed/RE1Ybuk]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a>Preparare Active Directory dalla Distribuzione guidata

1. Accedere come utente con le credenziali Schema Admins per il dominio di Active Directory.
    
2. Aprire la Distribuzione guidata di Skype for Business Server.
    
    > [!TIP]
    > Se si desidera esaminare i file di registro creati dalla Distribuzione guidata di Skype for Business Server, è possibile trovarli nel computer in cui è stata eseguita la Distribuzione guidata, nella directory Utenti dell'utente di Servizi di dominio Active Directory che ha eseguito il passaggio. Ad esempio, se l'utente ha eseguito l'accesso come amministratore di dominio nel dominio contoso.local, i file di registro si trovano in: C:\Users\Administrator.Contoso\AppData\Local\Temp. 
  
3. Fare clic **sul collegamento Prepara Active Directory.**
    
4. **Passaggio 1: Preparare lo schema**
    
    a. Esaminare le informazioni sui prerequisiti per il passaggio 1 a cui è possibile accedere facendo clic sull'elenco a discesa sotto il titolo Passaggio 1.
    
    b. Fare **clic su** Esegui nel passaggio 1 per avviare la preparazione guidata dello schema.
    
    c. Tenere presente che la procedura deve essere eseguita una sola volta per ogni distribuzione e quindi fare clic su **Avanti.**
    
    d. Dopo aver preparato lo schema, è possibile visualizzare il registro facendo clic **su Visualizza registro.** 
    
    e. Fare **clic su** Fine per chiudere la procedura guidata Preparazione schema e tornare alla procedura di preparazione di Active Directory.
    
5. **Passaggio 2: Verificare la replica della partizione dello schema**
    
    a. Accedere al controller di dominio per il dominio.
    
    b. Aprire **ADSI Edit** dal menu a discesa **Strumenti** in **Server Manager.**
    
    c. Scegliere **Connetti a** dal menu **Azione**.
    
    d. Nella finestra di dialogo **Impostazioni connessione** selezionare **Schema** in **Selezionare un contesto dei nomi noto** e quindi fare clic su **OK**.
    
    e. Nel contenitore dello schema cercare **CN=ms-RTC-SIP-SchemaVersion.** Se questo oggetto esiste e il valore dell'attributo **rangeUpper** è 1150 e il valore dell'attributo **rangeLower** è 3, lo schema è stato aggiornato e replicato correttamente. Se questo oggetto non esiste o i valori degli attributi **rangeUpper** e **rangeLower** non sono specificati, lo schema non è stato modificato o non è stato replicato.
    
6. **Passaggio 3: Preparare la foresta corrente**
    
    a. Esaminare le informazioni sui prerequisiti per il passaggio 3 a cui è possibile accedere facendo clic sull'elenco a discesa sotto il titolo Passaggio 3.
    
    b. Fare **clic su** Esegui nel passaggio 3 per avviare la procedura guidata Prepara foresta corrente.
    
    c. Tenere presente che la procedura deve essere eseguita una sola volta per ogni distribuzione e quindi fare clic su **Avanti.**
    
    d. Specificare il dominio in cui verranno creati i gruppi universali. Se il server fa parte del dominio, è possibile scegliere **Dominio locale** e fare clic su **Avanti.**
    
    e. Dopo aver preparato la foresta, è possibile visualizzare il registro facendo clic **su Visualizza registro.** 
    
    f. Fare **clic su** Fine per chiudere la procedura guidata Prepara foresta corrente e tornare alla procedura di preparazione di Active Directory.
    
    g. Fare **clic su Skype for Business Server Management Shell** dalla pagina **App** per avviare PowerShell.
    
    h. Digitare il comando Get-CsAdForest e premere **INVIO.**
    
    i. Se il risultato è **LC_FORESTSETTINGS_STATE_READY**, la foresta è stata preparata correttamente, come illustrato nella figura.
    
     ![Verificare la replica della foresta.](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. **Passaggio 4: Verificare la replica del catalogo globale**
    
    a. In un controller di dominio, preferibilmente in un sito remoto degli altri controller di dominio, aprire **Utenti e computer di Active Directory** nella foresta in cui è stata eseguita la relativa preparazione.
    
    b. In **Utenti e computer di Active Directory** espandere il nome di dominio della foresta o di un dominio figlio.
    
    c. Fare clic **sul** contenitore Utenti nel riquadro sinistro e cercare il gruppo universale **CsAdministrator** nel riquadro a destra. Se CsAdministrator (tra gli altri nuovi gruppi universali che iniziano con Cs) è presente, la replica di Active Directory ha avuto esito positivo.
    
    d. Se i gruppi non sono ancora presenti, è possibile forzare la replica oppure attendere 15 minuti e aggiornare il riquadro destro. La replica è completata quando i gruppi risultano presenti.
    
8. **Passaggio 5: Preparare il dominio corrente**
    
    a. Esaminare le informazioni sui prerequisiti per il passaggio 5.
    
    b. Fare **clic su** Esegui nel passaggio 5 per avviare la procedura guidata Prepara dominio corrente.
    
    c. Tenere presente che la procedura deve essere eseguita una sola volta per ogni dominio della distribuzione e quindi fare clic su **Avanti.**
    
    d. Dopo aver preparato il dominio, è possibile visualizzare il registro facendo clic **su Visualizza registro.** 
    
    e. Fare **clic su** Fine per chiudere la procedura guidata Preparazione dominio corrente e tornare alla procedura di preparazione di Active Directory.
    
    Questi passaggi devono essere completati in ogni dominio in cui vengono trovati oggetti di Skype for Business Server, altrimenti i servizi potrebbero non avviarsi. Sono inclusi qualsiasi tipo di oggetto di Active Directory, ad esempio utenti, oggetti contatto, gruppi amministrativi o qualsiasi altro tipo di oggetto. È possibile utilizzare Set-CsUserReplicatorConfiguration -ADDomainNamingContextList per aggiungere solo i domini con oggetti Skype for Business Server, se necessario.
    
9. **Passaggio 6: Verificare la replica nel dominio**
    
    a. Fare clic **su Skype for Business Server Management Shell** dalla pagina **App** per avviare PowerShell.
    
    b. Utilizzare il comando Get-CsAdDomain per verificare la replica all'interno del dominio.
    
   ```powershell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    > [!NOTE]
    > Se non si specifica il parametro Domain, per impostazione predefinita verrà utilizzato il dominio locale. 
  
    Esempio di esecuzione del comando per il dominio contoso.local:
    
   ```powershell
   Get-CsAdDomain -Domain contoso.local -GlobalSettingsDomainController dc.contoso.local
   ```

    > [!NOTE]
    > Utilizzando il parametro GlobalSettingsDomainController, è possibile indicare dove sono archiviate le impostazioni globali. Se le impostazioni sono archiviate nel contenitore System (tipico delle distribuzioni di aggiornamento in cui non è stata eseguita la migrazione dell'impostazione globale nel contenitore Configuration), devi definire un controller di dominio nella radice della foresta di Servizi di dominio Active Directory. Se invece le impostazioni globali sono incluse nel contenitore Configuration, come avviene in genere con le distribuzioni nuove o di aggiornamento per cui è stata eseguita la migrazione delle impostazioni nel contenitore Configuration, definire un controller di dominio nella foresta. Se non si specifica questo parametro, il cmdlet presuppone che le impostazioni siano archiviate nel contenitore Configuration e faccia riferimento a qualsiasi controller di dominio in Active Directory. 
  
    c. Se il risultato è **LC_DOMAINSETTINGS_STATE_READY**, il dominio è stato replicato correttamente.
    
10. **Passaggio 7: Aggiungere utenti per fornire l'accesso amministrativo al Pannello di controllo di Skype for Business Server**
    
    a. Eseguire l'accesso come membri del gruppo Domain Admins o del gruppo RTCUniversalServerAdmins.
    
    b. Aprire Utenti e **computer di Active Directory,** espandere il dominio, fare clic sul contenitore **Utenti,** fare clic con il pulsante destro del mouse su CSAdministrator e scegliere **Proprietà.**
    
    c. Nelle **** proprietà di CSAdministrators fare clic sulla scheda **Membri**.
    
    d. Nella scheda **Membri** fare clic su **Aggiungi**. In **Seleziona utenti, contatti, computer, account di servizio o gruppi** individuare **Immettere i nomi degli oggetti da selezionare**. Digitare i nomi degli utenti o dei gruppi da aggiungere al gruppo CSAdministrators. Fare clic su **OK**.
    
    e. Nella scheda **Membri** verificare che gli utenti o i gruppi selezionati siano presenti. Fare clic su **OK**.
    
    > [!CAUTION]
    > Il Pannello di controllo di Skype for Business Server è uno strumento di controllo degli accessi basato sui ruoli. L'appartenenza al gruppo CsAdministrator offre a un utente che utilizza il Pannello di controllo di Skype for Business Server il controllo completo per tutte le funzioni di configurazione disponibili. Vi sono inoltre altri ruoli per funzioni specifiche. Per informazioni dettagliate sui ruoli disponibili, vedere Requisiti ambientali per [Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o Requisiti server per Skype for Business Server [2019.](../../../SfBServer2019/plan/system-requirements.md) Si noti che non è necessario che gli utenti siano abilitati per Skype for Business Server per essere membri dei gruppi di gestione. 
  
    > [!CAUTION]
    > Per mantenere l'integrità del controllo di accesso basato sui ruoli e della sicurezza, aggiungere gli utenti ai gruppi che definiscono il ruolo che l'utente svolge nella gestione della distribuzione di Skype for Business Server. 
  
11. Disconnettersi, quindi accedere di nuovo a Windows in modo che il token di sicurezza sia aggiornato con il nuovo gruppo di sicurezza di Skype for Business Server e quindi riaprire la Distribuzione guidata.
    
12. Verificare che accanto a Prepara **Active Directory** sia visualizzato un segno di spunta verde per confermare l'esito positivo, come illustrato nella figura.
    
     ![Preparazione di Active Directory completata.](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

## <a name="see-also"></a>Vedere anche
 
[Servizi di dominio Active Directory per Skype for Business Server 2015](../../plan-your-deployment/security/active-directory-domain-services.md)
