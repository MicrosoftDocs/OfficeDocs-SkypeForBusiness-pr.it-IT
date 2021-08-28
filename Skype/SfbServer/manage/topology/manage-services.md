---
title: Gestire i servizi in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Informazioni su come visualizzare lo stato del servizio, avviare e arrestare i servizi e impedire sessioni per i servizi.
ms.openlocfilehash: 8c1f527e32d50624fddc1b4b261f6fbd20e97a47
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58604821"
---
# <a name="manage-services-in-skype-for-business-server"></a>Gestire i servizi in Skype for Business Server

È possibile utilizzare il Pannello di controllo di Skype for Business Server per visualizzare un elenco di tutti i computer che eseguono Skype for Business Server nella topologia, visualizzare lo stato dei servizi, avviare o arrestare i servizi e impedire sessioni per i servizi.

- [Visualizzare un elenco di computer che eseguono Skype for Business Server](#view-a-list-of-computers-running-skype-for-business-server)
- [Visualizzare lo stato dei servizi in esecuzione in un computer in Skype for Business](#view-the-status-of-services-running-on-a-computer-in-skype-for-business)
- [Avviare o arrestare Skype for Business servizi](#start-or-stop-skype-for-business-services)
- [Impedire le sessioni per i servizi](#prevent-sessions-for-services)

## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>Visualizzare un elenco di computer che eseguono Skype for Business Server

Utilizzare il Skype for Business Server di controllo per visualizzare un elenco di tutti i computer che eseguono Skype for Business nella topologia e visualizzare lo stato del servizio di ognuno di essi. È possibile ordinare l'elenco in base al computer, al pool o al sito. 

1. Da un account utente assegnato a uno dei ruoli amministrativi predefiniti per Skype for Business Server, accedere a qualsiasi computer nella distribuzione interna. Per ulteriori informazioni, vedere [Role-based access control (RBAC) for Skype for Business Server](../../plan-your-deployment/security/role-based-access-control-rbac.md).
2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il Skype for Business Server di controllo, vedere [Installare e aprire gli strumenti di amministrazione.](../../management-tools/install-and-open-administrative-tools.md)
3. Sulla barra di spostamento sinistra fare clic su **Topologia** e quindi su **Stato**.
4. Nella pagina Stato eseguire una delle operazioni seguenti in base alle esigenze:
    - Ordinare l'elenco facendo clic sull'intestazione di colonna **Computer**, **Pool** o **Sito** e quindi sulla freccia verso l'alto o verso il basso.
    - Fare clic su **Aggiorna** per visualizzare l'elenco più aggiornato.
    - Cercare un computer specifico digitando il relativo nome nel campo di ricerca.
   
## <a name="view-the-status-of-services-running-on-a-computer-in-skype-for-business"></a>Visualizzare lo stato dei servizi in esecuzione in un computer in Skype for Business

Utilizzare il Skype for Business Server di controllo per visualizzare tutti i servizi in esecuzione in un computer specifico della topologia di Skype for Business Server e visualizzare lo stato di ogni servizio.

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
2. Aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il Pannello di controllo. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il Skype for Business Server di controllo, vedere [Installare e aprire gli strumenti di amministrazione.](../../management-tools/install-and-open-administrative-tools.md)
3. Sulla barra di spostamento sinistra fare clic su **Topologia**.
4. Nella pagina Stato ordinare l'elenco oppure effettuare una ricerca per trovare il computer desiderato e fare clic sul nome del computer.
5. Eseguire una delle operazioni seguenti:
    - Per visualizzare lo stato più recente dei servizi in esecuzione sul computer, fare clic su **Ottieni stato servizio**.
    - Per visualizzare un elenco di servizi specifici in esecuzione sul computer e lo stato di ogni servizio, fare clic su **Proprietà** e quindi su **Chiudi** per tornare all'elenco.

### <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a>Visualizzazione dello stato del servizio tramite Windows PowerShell cmdlet

È inoltre possibile visualizzare lo stato del servizio utilizzando Windows PowerShell e il cmdlet Get-CsWindowsService servizio. È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per ulteriori informazioni, vedere [Skype for Business Server Management Shell](../management-shell.md).

**Per visualizzare lo stato del servizio**

Per visualizzare lo stato del servizio in un computer, digitare un comando simile al seguente in Skype for Business Server Management Shell e quindi premere INVIO:

```powershell
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

Il comando restituisce informazioni simili a quelle riportate di seguito:

```console
RoleName                                  Status
--------                                  ------
{W3SVC}                                   Running
{CentralManagement}                       Running
{ClsAgent}                                Running
{Registrar, UserServer, EdgeServer}       Running
{ApplicationServer}                       Running
{ConferencingServer}                      Running
{MediationServer}                         Running
```

Per informazioni dettagliate, [vedere Get-CsWindowsService](/powershell/module/skype/Get-CsWindowsService).

## <a name="start-or-stop-skype-for-business-services"></a>Avviare o arrestare Skype for Business servizi

Utilizzare il Skype for Business Server di controllo per avviare o arrestare tutti i servizi di Skype for Business Server in esecuzione in un computer specifico oppure per avviare o arrestare un servizio specifico.

### <a name="start-or-stop-all-skype-for-business-server-services-on-a-computer"></a>Avviare o arrestare tutti i Skype for Business Server in un computer

1. Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer nella rete in cui è stato distribuito Skype for Business Server. È possibile determinare se è stato assegnato il ruolo CsServerAdministrator o CsAdministrator RBAC eseguendo un comando simile al seguente:

    ```powershell
    Get-CsAdminRoleAssignment -Identity "kenmyer"`
    ```

2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il Skype for Business Server di controllo, vedere [Installare e aprire gli strumenti di amministrazione.](../../management-tools/install-and-open-administrative-tools.md)
3. Sulla barra di spostamento sinistra fare clic su **Topologia** e quindi su **Stato**.
4. Nella pagina Stato ordinare o scorrere l'elenco per trovare il computer in cui sono in esecuzione i servizi che si desidera avviare o arrestare e quindi fare clic su di esso.
5. Fare clic su **Azione**.
6. Fare clic su **Avvia tutti i servizi** o **Arresta tutti i servizi**.

### <a name="start-or-stop-a-specific-service"></a>Avviare o arrestare un servizio specifico

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
2. Aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il Pannello di controllo. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il Skype for Business Server di controllo, vedere [Installare e aprire gli strumenti di amministrazione.](../../management-tools/install-and-open-administrative-tools.md)
3. Sulla barra di spostamento sinistra fare clic su **Topologia** e quindi su **Stato**.
4. Nella pagina Stato ordinare o scorrere l'elenco per trovare il computer in cui è in esecuzione il servizio che si desidera avviare o arrestare e quindi fare clic su di esso.
5. Fare clic su **Proprietà**.
6. Ordinare l'elenco dei servizi, se necessario, e fare clic sul servizio da avviare o arrestare.
7. Fare clic su **Azione**.
8. Fare clic su **Avvia servizio** o **Arresta servizio**.
9. Fare clic su **Chiudi**.


## <a name="prevent-sessions-for-services"></a>Impedire le sessioni per i servizi

Utilizzare il Skype for Business di controllo per impedire nuove sessioni per tutti i servizi Skype for Business Server in esecuzione in un computer specifico o per impedire nuove sessioni per un servizio specifico.

### <a name="prevent-new-sessions-for-all--skype-for-business-server-services-on-a-computer"></a>Impedire nuove sessioni per tutti i Skype for Business Server in un computer

1. Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer nella rete in cui è stato distribuito Skype for Business Server.
2. Aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il Pannello di controllo. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il Skype for Business Server di controllo, vedere [Installare e aprire gli strumenti di amministrazione.](../../management-tools/install-and-open-administrative-tools.md)
3. Nella barra di spostamento sinistra fare clic su **Topologia** e quindi su **Stato**.
4. Nella pagina Stato ordinare l'elenco oppure cercare nell'elenco il computer in cui sono in esecuzione i servizi per cui si desidera impedire nuove sessioni, quindi fare clic su di esso.
5. Fare clic su **Azione**.
6. Fare clic su **Impedisci nuove sessioni per tutti i servizi**.

### <a name="prevent-new-sessions-for-a-specific-service"></a>Impedire nuove sessioni per un servizio specifico

1. Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer nella rete in cui è stato distribuito Skype for Business Server.
2. Aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il Pannello di controllo. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il Skype for Business Server di controllo, vedere [Installare e aprire gli strumenti di amministrazione.](../../management-tools/install-and-open-administrative-tools.md)
3. Sulla barra di spostamento sinistra fare clic su **Topologia** e quindi su **Stato**.
4. Fare clic su **Proprietà**.
5. Ordinare l'elenco dei servizi, se necessario, quindi fare clic sul servizio per cui si desidera impedire nuove sessioni.
6. Fare clic su **Azione**.
7. Fare clic su **Impedisci nuove sessioni per il servizio**.
8. Fare clic su **Chiudi**.