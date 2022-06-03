---
title: 'Skype for Business Server: Preparare Active Directory'
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985077a4-c8e1-4d5a-9fcf-fef41cf6d61d
description: "Riepilogo: informazioni su come preparare il dominio di Active Directory per un'installazione di Skype for Business Server."
ms.openlocfilehash: b40eccab3d2f71e5211a1c67342440a86497023d
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860574"
---
# <a name="skype-for-business-server-prepare-active-directory"></a>Skype for Business Server: Preparare Active Directory
 
**Riepilogo:** Informazioni su come preparare il dominio di Active Directory per un'installazione di Skype for Business Server.
  
Skype for Business Server lavora a stretto contatto con Active Directory. È necessario preparare il dominio di Active Directory per l'uso con Skype for Business Server. Questo processo viene eseguito nella Distribuzione guidata e viene eseguito una sola volta per il dominio. Questo avviene perché il processo crea gruppi e modifica il dominio ed è necessario eseguire questa operazione una sola volta. È possibile eseguire i passaggi da 1 a 5 in qualsiasi ordine. Tuttavia, è necessario eseguire i passaggi 6, 7 e 8 nell'ordine e dopo i passaggi da 1 a 5, come descritto nel diagramma. La preparazione di Active Directory è il passaggio 4 dell'8. Per altre informazioni sulla pianificazione per Active Directory, vedere [Requisiti ambientali per Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o [Requisiti del server per Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
  
![diagramma di panoramica.](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a>Preparazione di Active Directory

Skype for Business Server è strettamente integrato con Active Directory Domain Services (AD DS). Prima di installare Skype for Business Server per la prima volta, è necessario preparare Active Directory. La sezione della Distribuzione guidata intitolata **Preparare Active Directory** prepara l'ambiente Active Directory per l'uso con Skype for Business Server.
  
> [!NOTE]
> Skype for Business Server usa (Ad DS) per tenere traccia e comunicare con tutti i server in una topologia. La maggior parte di questi server deve essere aggiunta al dominio in modo che Skype for Business Server possa funzionare correttamente. Tenere presente che server come Edge e Proxy inverso non devono essere aggiunti a un dominio.
  
> [!IMPORTANT]
> La procedura Prepara Active Directory deve essere eseguita una sola volta per ogni dominio della distribuzione. 
  
Guardare i passaggi video per **Preparare Active Directory**:
  
> [!video https://www.microsoft.com/videoplayer/embed/RE1Ybuk]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a>Preparare Active Directory dalla Distribuzione guidata

1. Accedere come utente con le credenziali degli amministratori dello schema per il dominio di Active Directory.
    
2. Aprire Skype for Business Server Distribuzione guidata.
    
    > [!TIP]
    > Per esaminare i file di log creati dalla Distribuzione guidata Skype for Business Server, è possibile trovarli nel computer in cui è stata eseguita la Distribuzione guidata, nella directory Utenti dell'utente di Active Directory Domain Services che ha eseguito il passaggio. Ad esempio, se l'utente ha eseguito l'accesso come amministratore di dominio nel dominio contoso.local, i file di log si trovano in: C:\Users\Administrator.Contoso\AppData\Local\Temp. 
  
3. Fare clic sul collegamento **Prepara Active Directory** .
    
4. **Passaggio 1: Preparare lo schema**
    
    a. Esaminare le informazioni sui prerequisiti per il passaggio 1 a cui è possibile accedere facendo clic sull'elenco a discesa sotto il titolo Passaggio 1.
    
    b. Fare clic su **Esegui** nel passaggio 1 per avviare la procedura guidata Prepara schema.
    
    c. Si noti che la procedura deve essere eseguita una sola volta per ogni distribuzione e quindi fare clic su **Avanti**.
    
    d. Dopo aver preparato lo schema, è possibile visualizzare il log facendo clic su **Visualizza log**. 
    
    e. Fare clic su **Fine** per chiudere la procedura guidata Prepara schema e tornare alla procedura Prepara Active Directory.
    
5. **Passaggio 2: Verificare la replica della partizione dello schema**
    
    a. Accedere al controller di dominio per il dominio.
    
    b. Aprire **Modifica ADSI** dal menu a discesa **Strumenti** in **Server Manager**.
    
    c. Scegliere **Connetti a** dal menu **Azione**.
    
    d. Nella finestra di dialogo **Impostazioni connessione** selezionare **Schema** in **Selezionare un contesto dei nomi noto** e quindi fare clic su **OK**.
    
    e. Nel contenitore dello schema cercare **CN=ms-RTC-SIP-SchemaVersion**. Se questo oggetto esiste e il valore dell'attributo **rangeUpper** è 1150 e il valore dell'attributo **rangeLower** è 3, lo schema è stato aggiornato e replicato correttamente. Se questo oggetto non esiste o i valori degli attributi **rangeUpper** e **rangeLower** non sono come specificati, lo schema non è stato modificato o non è stato replicato.
    
6. **Passaggio 3: Preparare la foresta corrente**
    
    a. Esaminare le informazioni sui prerequisiti per il passaggio 3 a cui è possibile accedere facendo clic sull'elenco a discesa sotto il titolo Passaggio 3.
    
    b. Fare clic su **Esegui** nel passaggio 3 per avviare la procedura guidata Prepara foresta corrente.
    
    c. Si noti che la procedura deve essere eseguita una sola volta per ogni distribuzione e quindi fare clic su **Avanti**.
    
    d. Specificare il dominio in cui verranno creati i gruppi universali. Se il server fa parte del dominio, è possibile scegliere **Dominio locale** e fare clic su **Avanti**.
    
    e. Dopo aver preparato la foresta, è possibile visualizzare il log facendo clic su **Visualizza log**. 
    
    f. Fare clic su **Fine** per chiudere la procedura guidata Prepara foresta corrente e tornare alla procedura Prepara Active Directory.
    
    g. Fare clic su **Skype for Business Server Management Shell** dalla pagina **App** per avviare PowerShell.
    
    h. Digitare il comando Get-CsAdForest e premere **INVIO**.
    
    i. Se il risultato è **LC_FORESTSETTINGS_STATE_READY**, la foresta è stata preparata correttamente, come illustrato nella figura.
    
     ![Verificare la replica della foresta.](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. **Passaggio 4: Verificare la replica del catalogo globale**
    
    a. In un controller di dominio, preferibilmente in un sito remoto degli altri controller di dominio, aprire **Utenti e computer di Active Directory** nella foresta in cui è stata eseguita la relativa preparazione.
    
    b. In **Utenti e computer di Active Directory** espandere il nome di dominio della foresta o di un dominio figlio.
    
    c. Fare clic sul contenitore **Utenti** nel riquadro sinistro e cercare il gruppo universale **CsAdministrator** nel riquadro a destra. Se CsAdministrator (tra gli altri nuovi gruppi universali che iniziano con Cs) è presente, la replica di Active Directory ha avuto esito positivo.
    
    d. Se i gruppi non sono ancora presenti, è possibile forzare la replica o attendere 15 minuti e aggiornare il riquadro a destra. La replica è completata quando i gruppi risultano presenti.
    
8. **Passaggio 5: Preparare il dominio corrente**
    
    a. Esaminare le informazioni sui prerequisiti per il passaggio 5.
    
    b. Fare clic su **Esegui** nel passaggio 5 per avviare la procedura guidata Prepara dominio corrente.
    
    c. Si noti che la procedura deve essere eseguita una sola volta per ogni dominio nella distribuzione e quindi fare clic su **Avanti**.
    
    d. Dopo aver preparato il dominio, è possibile visualizzare il log facendo clic su **Visualizza log**. 
    
    e. Fare clic su **Fine** per chiudere la procedura guidata Prepara dominio corrente e tornare alla procedura Prepara Active Directory.
    
    Questi passaggi devono essere completati in ogni dominio in cui vengono trovati oggetti Skype for Business Server, altrimenti i servizi potrebbero non essere avviati. Sono inclusi qualsiasi tipo di oggetto active directory, ad esempio utenti, oggetti contatto, gruppi amministrativi o qualsiasi altro tipo di oggetto. È possibile usare Set-CsUserReplicatorConfiguration -ADDomainNamingContextList per aggiungere solo i domini con oggetti Skype for Business Server, se necessario.
    
9. **Passaggio 6: Verificare la replica nel dominio**
    
    a. Fare clic sulla **Skype for Business Server Management Shell** dalla pagina **App** per avviare PowerShell.
    
    b. Usare il comando Get-CsAdDomain per verificare la replica all'interno del dominio.
    
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
    > Usando il parametro GlobalSettingsDomainController, è possibile indicare dove sono archiviate le impostazioni globali. Se le impostazioni vengono archiviate nel contenitore di sistema (tipico delle distribuzioni di aggiornamento che non hanno avuto l'impostazione globale migrata nel contenitore di configurazione), si definisce un controller di dominio nella radice della foresta di Servizi di dominio Active Directory. Se invece le impostazioni globali sono incluse nel contenitore Configuration, come avviene in genere con le distribuzioni nuove o di aggiornamento per cui è stata eseguita la migrazione delle impostazioni nel contenitore Configuration, definire un controller di dominio nella foresta. Se non si specifica questo parametro, il cmdlet presuppone che le impostazioni siano archiviate nel contenitore Configuration e faccia riferimento a qualsiasi controller di dominio in Active Directory. 
  
    c. Se il risultato è **LC_DOMAINSETTINGS_STATE_READY**, il dominio è stato replicato correttamente.
    
10. **Passaggio 7: Aggiungere utenti per fornire l'accesso amministrativo alla Skype for Business Server Pannello di controllo**
    
    a. Eseguire l'accesso come membri del gruppo Domain Admins o del gruppo RTCUniversalServerAdmins.
    
    b. Aprire **Utenti e computer di Active Directory**, espandere il dominio, fare clic sul contenitore **Utenti**, fare clic con il pulsante destro del mouse su CSAdministrator e scegliere **Proprietà**.
    
    c. Nelle **** proprietà di CSAdministrators fare clic sulla scheda **Membri**.
    
    d. Nella scheda **Membri** fare clic su **Aggiungi**. In **Seleziona utenti, contatti, computer, account di servizio o gruppi** individuare **Immettere i nomi degli oggetti da selezionare**. Digitare i nomi degli utenti o dei gruppi da aggiungere al gruppo CSAdministrators. Fare clic su **OK**.
    
    e. Nella scheda **Membri** verificare che gli utenti o i gruppi selezionati siano presenti. Fare clic su **OK**.
    
    > [!CAUTION]
    > Il Skype for Business Server Pannello di controllo è uno strumento di controllo degli accessi in base al ruolo. L'appartenenza al gruppo CsAdministrator offre a un utente che usa il controllo completo Skype for Business Server Pannello di controllo per tutte le funzioni di configurazione disponibili. Vi sono inoltre altri ruoli per funzioni specifiche. Per informazioni dettagliate sui ruoli disponibili, vedere [Requisiti ambientali per Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o [Requisiti del server per Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md). Si noti che gli utenti non devono essere abilitati per Skype for Business Server per essere resi membri dei gruppi di gestione. 
  
    > [!CAUTION]
    > Per mantenere la sicurezza e l'integrità del controllo degli accessi in base al ruolo, aggiungere utenti ai gruppi che definiscono il ruolo che l'utente svolge nella gestione della distribuzione Skype for Business Server. 
  
11. Disconnettersi e quindi accedere nuovamente a Windows in modo che il token di sicurezza venga aggiornato con il nuovo gruppo di sicurezza Skype for Business Server e quindi riaprire la Distribuzione guidata.
    
12. Verificare di visualizzare un segno di spunta verde accanto a **Preparare Active Directory** per confermare l'esito positivo, come illustrato nella figura.
    
     ![Preparare Active Directory completato.](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

## <a name="see-also"></a>Vedere anche
 
[Active Directory Domain Services per Skype for Business Server 2015](../../plan-your-deployment/security/active-directory-domain-services.md)
