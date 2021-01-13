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
description: "Riepilogo: informazioni su come preparare il dominio di Active Directory per un'installazione di Skype for Business Server. Scaricare una versione di valutazione gratuita di Skype for Business Server da Microsoft Evaluation Center all'indirizzo: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server ."
ms.openlocfilehash: 6196855ffeaf33fbea11c47d56c620e3df9195ee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801676"
---
# <a name="prepare-active-directory-for-skype-for-business-server"></a>Preparare Active Directory per Skype for Business Server
 
**Riepilogo:** Informazioni su come preparare il dominio Active Directory per un'installazione di Skype for Business Server. Scaricare una versione di valutazione gratuita di Skype for Business Server da [Microsoft Evaluation Center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Skype for Business Server è compatibile con Active Directory. È necessario preparare il dominio di Active Directory per l'utilizzo con Skype for Business Server. Questo processo viene eseguito nella distribuzione guidata e viene eseguito solo una volta per il dominio. Ciò è dovuto al fatto che il processo crea gruppi e modifica il dominio ed è necessario farlo solo una volta. È possibile eseguire i passaggi da 1 a 5 in qualsiasi ordine. Tuttavia, è necessario eseguire i passaggi 6, 7 e 8 nell'ordine e dopo i passaggi da 1 a 5, come indicato nel diagramma. La preparazione di Active Directory è il passaggio 4 di 8. Per ulteriori informazioni sulla pianificazione di Active Directory, vedere [requisiti ambientali per Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o [requisiti del server per Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
  
![diagramma Panoramica](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a>Preparazione di Active Directory

Skype for Business Server è strettamente integrato con servizi di dominio Active Directory (AD DS). Prima di poter installare Skype for Business Server per la prima volta, è necessario preparare Active Directory. La sezione della distribuzione guidata intitolata **preparare Active Directory** prepara l'ambiente Active Directory per l'utilizzo con Skype for Business Server.
  
> [!NOTE]
> Skype for Business Server utilizza (AD DS) per monitorare e comunicare con tutti i server in una topologia. La maggior parte di questi server deve essere aggiunta al dominio in modo che Skype for Business Server possa funzionare correttamente. Tenere presente che i server come proxy inverso e Edge non devono essere aggiunti al dominio.
  
> [!IMPORTANT]
> La procedura di preparazione di Active Directory deve essere eseguita una sola volta per ogni dominio della distribuzione. 
  
Guardare i passaggi video per **preparare Active Directory**:
  
> [!video https://www.microsoft.com/videoplayer/embed/RE1Ybuk]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a>Preparare Active Directory dalla distribuzione guidata

1. Accedere come utente con le credenziali degli amministratori dello schema per il dominio di Active Directory.
    
2. Aprire la distribuzione guidata di Skype for Business Server.
    
    > [!TIP]
    > Se si desidera esaminare i file di registro creati dalla distribuzione guidata di Skype for Business Server, è possibile trovarli nel computer in cui è stata eseguita la distribuzione guidata, nella directory degli utenti dell'utente di servizi di dominio Active Directory che ha eseguito il passaggio. Ad esempio, se l'utente ha effettuato l'accesso come amministratore del dominio nel dominio contoso. local, i file di registro sono disponibili in: C:\Users\Administrator.Contoso\AppData\Local\Temp. 
  
3. Fare clic sul collegamento **prepara Active Directory** .
    
4. **Passaggio 1: preparare lo schema**
    
    a. Rivedere le informazioni sui prerequisiti per il passaggio 1, a cui è possibile accedere facendo clic sull'elenco a discesa sotto il titolo del passaggio 1.
    
    b. Fare clic su **Esegui** nel passaggio 1 per avviare la procedura guidata preparazione schema.
    
    c. Tenere presente che la procedura deve essere eseguita una sola volta per ogni distribuzione e quindi fare clic su **Avanti**.
    
    d. Dopo aver preparato lo schema, è possibile visualizzare il registro facendo clic su **Visualizza registro**. 
    
    e. Fare clic su **fine** per chiudere la procedura guidata Prepara schema e tornare alla procedura di preparazione di Active Directory.
    
5. **Passaggio 2: verificare la replica della partizione dello schema**
    
    a. Accedere al controller di dominio per il dominio.
    
    b. Aprire **ADSI Edit** dal menu a discesa **strumenti** in **Server Manager**.
    
    c. Scegliere **Connetti a** dal menu **Azione**.
    
    d. Nella finestra di dialogo **Impostazioni connessione** selezionare **Schema** in **Selezionare un contesto dei nomi noto** e quindi fare clic su **OK**.
    
    e. Sotto il contenitore dello schema, cercare **CN = ms-RTC-SIP-SchemaVersion**. Se l'oggetto esiste e il valore dell'attributo **rangeUpper** è 1150 e il valore dell'attributo **RangeLower** è 3, lo schema è stato aggiornato e replicato correttamente. Se l'oggetto non esiste o se i valori degli attributi **rangeUpper** e **RangeLower** non sono specificati, lo schema non è stato modificato o non è stato replicato.
    
6. **Passaggio 3: preparare la foresta corrente**
    
    a. Rivedere le informazioni sui prerequisiti per il passaggio 3 a cui è possibile accedere facendo clic sull'elenco a discesa sotto il titolo del passaggio 3.
    
    b. Fare clic su **Esegui** nel passaggio 3 per avviare la procedura guidata prepara foresta corrente.
    
    c. Tenere presente che la procedura deve essere eseguita solo una volta per ogni distribuzione e quindi fare clic su **Avanti**.
    
    d. Specificare il dominio in cui verranno creati i gruppi universali. Se il server fa parte del dominio, è possibile scegliere **dominio locale** e fare clic su **Avanti**.
    
    e. Dopo la preparazione della foresta, è possibile visualizzare il registro facendo clic su **Visualizza registro**. 
    
    f. Fare clic su **fine** per chiudere la procedura guidata prepara foresta corrente e tornare alla procedura di preparazione di Active Directory.
    
    g. Fare clic su **Skype for Business Server Management Shell** dalla pagina **Apps** per avviare PowerShell.
    
    h. Digitare il comando Get-CsAdForest e premere **invio**.
    
    i. Se il risultato è **LC_FORESTSETTINGS_STATE_READY**, la foresta è stata preparata correttamente, come mostrato nella figura.
    
     ![Verificare la replica della foresta.](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. **Passaggio 4: verificare la replica del catalogo globale**
    
    a. In un controller di dominio, preferibilmente in un sito remoto degli altri controller di dominio, aprire **Utenti e computer di Active Directory** nella foresta in cui è stata eseguita la relativa preparazione.
    
    b. In **Utenti e computer di Active Directory** espandere il nome di dominio della foresta o di un dominio figlio.
    
    c. Fare clic sul contenitore **utenti** nel riquadro sinistro e cercare il gruppo universale **CsAdministrator** nel riquadro a destra. Se CsAdministrator (tra gli altri nuovi gruppi universali che iniziano con CS) è presente, la replica di Active Directory ha avuto esito positivo.
    
    d. Se i gruppi non sono ancora presenti, è possibile forzare la replica oppure attendere 15 minuti e aggiornare il riquadro laterale destro. La replica è completata quando i gruppi risultano presenti.
    
8. **Passaggio 5: preparare il dominio corrente**
    
    a. Rivedere le informazioni sui prerequisiti per il passaggio 5.
    
    b. Fare clic su **Esegui** nel passaggio 5 per avviare la procedura guidata Prepara dominio corrente.
    
    c. Tenere presente che la procedura deve essere eseguita una sola volta per ogni dominio nella distribuzione e quindi fare clic su **Avanti**.
    
    d. Dopo aver preparato il dominio, è possibile visualizzare il registro facendo clic su **Visualizza registro**. 
    
    e. Fare clic su **fine** per chiudere la procedura guidata preparazione del dominio corrente e tornare alla procedura di preparazione di Active Directory.
    
    Questi passaggi devono essere completati in tutti i domini in cui vengono trovati gli oggetti di Skype for Business Server, altrimenti i servizi potrebbero non essere avviati. Sono inclusi tutti i tipi di oggetti di Active Directory, ad esempio utenti, oggetti contatto, gruppi amministrativi o qualsiasi altro tipo di oggetto. Se necessario, è possibile utilizzare Set-CsUserReplicatorConfiguration-ADDomainNamingContextList per aggiungere solo i domini con gli oggetti di Skype for Business Server.
    
9. **Passaggio 6: verificare la replica nel dominio**
    
    a. Fare clic su **Skype for Business Server Management Shell** dalla pagina **Apps** per avviare PowerShell.
    
    b. Utilizzare il comando Get-CsAdDomain per verificare la replica all'interno del dominio.
    
   ```powershell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    > [!NOTE]
    > Se non si specifica il parametro Domain, per impostazione predefinita verrà utilizzato il dominio locale. 
  
    Esempio di esecuzione del comando per il dominio contoso. local:
    
   ```powershell
   Get-CsAdDomain -Domain contoso.local -GlobalSettingsDomainController dc.contoso.local
   ```

    > [!NOTE]
    > Se si utilizza il parametro GlobalSettingsDomainController, è possibile indicare la posizione in cui vengono archiviate le impostazioni globali. Se le impostazioni vengono archiviate nel contenitore di sistema (tipica delle distribuzioni di aggiornamento che non hanno eseguito la migrazione dell'impostazione globale nel contenitore di configurazione), è possibile definire un controller di dominio nella radice della foresta di AD DS. Se invece le impostazioni globali sono incluse nel contenitore Configuration, come avviene in genere con le distribuzioni nuove o di aggiornamento per cui è stata eseguita la migrazione delle impostazioni nel contenitore Configuration, definire un controller di dominio nella foresta. Se non si specifica questo parametro, il cmdlet presuppone che le impostazioni siano archiviate nel contenitore di configurazione e si riferisca a qualsiasi controller di dominio in Active Directory. 
  
    c. Se il risultato è **LC_DOMAINSETTINGS_STATE_READY**, il dominio è stato replicato correttamente.
    
10. **Passaggio 7: aggiungere gli utenti per fornire l'accesso amministrativo al pannello di controllo di Skype for Business Server**
    
    a. Eseguire l'accesso come membri del gruppo Domain Admins o del gruppo RTCUniversalServerAdmins.
    
    b. Aprire **utenti e computer di Active Directory**, espandere il proprio dominio, fare clic sul contenitore **degli utenti** , fare clic con il pulsante destro del mouse su CsAdministrator e scegliere **proprietà**.
    
    c. Nelle **** proprietà di CSAdministrators fare clic sulla scheda **Membri**.
    
    d. Nella scheda **Membri** fare clic su **Aggiungi**. In **Seleziona utenti, contatti, computer, account di servizio o gruppi** individuare **Immettere i nomi degli oggetti da selezionare**. Digitare i nomi degli utenti o dei gruppi da aggiungere al gruppo CSAdministrators. Fare clic su **OK**.
    
    e. Nella scheda **membri** , verificare che gli utenti o i gruppi selezionati siano presenti. Fare clic su **OK**.
    
    > [!CAUTION]
    > Il pannello di controllo di Skype for Business Server è uno strumento di controllo di accesso basato sui ruoli. L'appartenenza al gruppo CsAdministrator fornisce a un utente che utilizza il controllo completo del pannello di controllo di Skype for Business Server per tutte le funzioni di configurazione disponibili. Vi sono inoltre altri ruoli per funzioni specifiche. Per informazioni dettagliate sui ruoli disponibili, vedere Requisiti [ambientali per Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o [requisiti del server per Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md). Si noti che gli utenti non devono essere abilitati per Skype for Business Server per essere resi membri dei gruppi di gestione. 
  
    > [!CAUTION]
    > Per mantenere la sicurezza e l'integrità del controllo di accesso basato sui ruoli, aggiungere gli utenti ai gruppi che definiscono il ruolo eseguito dall'utente nella gestione della distribuzione di Skype for Business Server. 
  
11. Disconnettersi e quindi eseguire nuovamente l'accesso a Windows in modo che il token di sicurezza venga aggiornato con il nuovo gruppo di sicurezza Skype for Business Server e quindi riaprire la distribuzione guidata.
    
12. Verificare che sia visualizzato un segno di spunta verde accanto a **prepara Active Directory** per confermare l'esito positivo, come mostrato nella figura.
    
     ![Preparare Active Directory completata.](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

## <a name="see-also"></a>Vedere anche
 
[Servizi di dominio Active Directory per Skype for Business Server 2015](../../plan-your-deployment/security/active-directory-domain-services.md)
