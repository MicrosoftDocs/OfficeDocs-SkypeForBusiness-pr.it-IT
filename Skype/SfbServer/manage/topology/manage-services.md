---
title: Gestire i servizi in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Informazioni su come visualizzare lo stato del servizio, avviare e arrestare i servizi e impedire sessioni per i servizi.
ms.openlocfilehash: 154c7b2d5ff858e22be4159ec1797ef6a6724445
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817117"
---
# <a name="manage-services-in-skype-for-business-server"></a>Gestire i servizi in Skype for Business Server

È possibile usare il pannello di controllo di Skype for Business Server per visualizzare un elenco di tutti i computer che eseguono Skype for Business Server nella topologia, visualizzare lo stato dei servizi, avviare o arrestare i servizi e impedire sessioni per i servizi.

- [Visualizzare un elenco di computer che eseguono Skype for Business Server](#view-a-list-of-computers-running-skype-for-business-server)
- [Visualizzare lo stato dei servizi in uso in un computer in Skype for business](#view-the-status-of-services-running-on-a-computer-in-skype-for-business)
- [Avviare o arrestare i servizi Skype for business](#start-or-stop-skype-for-business-services)
- [Impedire le sessioni per i servizi](#prevent-sessions-for-services)

## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>Visualizzare un elenco di computer che eseguono Skype for Business Server

Usa il pannello di controllo di Skype for Business Server per visualizzare un elenco di tutti i computer che eseguono Skype for business nella tua topologia e vedere lo stato del servizio di ognuno di essi. È possibile ordinare l'elenco in base al computer, al pool o al sito. 

1. Da un account utente assegnato a uno dei ruoli amministrativi predefiniti per Skype for Business Server, accedere a qualsiasi computer della distribuzione interna. Per altre informazioni, Vedi [controllo di accesso basato sui ruoli (RBAC) per Skype for Business Server](../../plan-your-deployment/security/role-based-access-control-rbac.md).
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Skype for Business Server, vedere [installare e aprire gli strumenti di amministrazione](../../management-tools/install-and-open-administrative-tools.md).
3. Nella barra di spostamento sinistra fare clic su **topologia**e quindi su **stato**.
4. Nella pagina stato eseguire una delle operazioni seguenti in base alle esigenze:
    - Ordinare l'elenco facendo clic sul titolo del **computer**, del **pool**o della colonna del **sito** , quindi facendo clic sulla freccia su o freccia giù.
    - Fare clic su **Aggiorna** per visualizzare l'elenco più aggiornato.
    - Cercare un computer specifico digitando il nome del computer nel campo di ricerca.
   
## <a name="view-the-status-of-services-running-on-a-computer-in-skype-for-business"></a>Visualizzare lo stato dei servizi in uso in un computer in Skype for business

Usare il pannello di controllo di Skype for Business Server per visualizzare tutti i servizi in uso in un computer specifico nella topologia di Skype for Business Server e vedere lo stato di ogni servizio.

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Skype for Business Server, vedere [installare e aprire gli strumenti di amministrazione](../../management-tools/install-and-open-administrative-tools.md).
3. Nella barra di spostamento sinistra fare clic su **topologia**.
4. Nella pagina Stato ordinare o cercare l'elenco, se necessario, per trovare il computer interessato e quindi fare clic sul nome del computer.
5. Eseguire una delle operazioni seguenti:
    - Per visualizzare lo stato più recente dei servizi in uso nel computer, fare clic su **Ottieni stato servizio**.
    - Per visualizzare un elenco di servizi specifici in uso nel computer e lo stato di ogni servizio, fare clic su **Proprietà**e quindi su **Chiudi** per tornare all'elenco.

### <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a>Visualizzazione dello stato del servizio tramite i cmdlet di Windows PowerShell

È anche possibile visualizzare lo stato del servizio tramite Windows PowerShell e il cmdlet Get-CsWindowsService. Puoi eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per altre informazioni, Vedi [Skype for Business Server Management Shell](../management-shell.md).

**Per visualizzare lo stato del servizio**

Per visualizzare lo stato del servizio in un computer, digitare un comando simile al seguente in Skype for Business Server Management Shell e quindi premere INVIO:

`Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status`

Questo comando restituisce informazioni simili a quelle seguenti:

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

Per informazioni dettagliate, vedere [Get-CsWindowsService](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsWindowsService).

## <a name="start-or-stop-skype-for-business-services"></a>Avviare o arrestare i servizi Skype for business

Usare il pannello di controllo di Skype for Business Server per avviare o arrestare tutti i servizi di Skype for Business Server in uso in un computer specifico oppure per avviare o arrestare un servizio specifico.

### <a name="start-or-stop-all-skype-for-business-server-services-on-a-computer"></a>Avviare o arrestare tutti i servizi di Skype for Business Server in un computer

1. Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. . Per determinare se è stato assegnato il ruolo CsServerAdministrator o CsAdministrator RBAC, è possibile eseguire un comando simile al seguente:

    `Get-CsAdminRoleAssignment -Identity "kenmyer"`

2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Skype for Business Server, vedere [installare e aprire gli strumenti di amministrazione](../../management-tools/install-and-open-administrative-tools.md).
3. Nella barra di spostamento sinistra fare clic su **topologia**e quindi su **stato**.
4. Nella pagina Stato ordinare o cercare l'elenco in base alle esigenze per trovare il computer in cui sono in esecuzione i servizi che si desidera avviare o arrestare e quindi fare clic su di esso.
5. Fare clic su **azione**.
6. Fare clic su **Avvia tutti i servizi** o **arrestare tutti i servizi**.

### <a name="start-or-stop-a-specific-service"></a>Avviare o arrestare un servizio specifico

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Skype for Business Server, vedere [installare e aprire gli strumenti di amministrazione](../../management-tools/install-and-open-administrative-tools.md).
3. Nella barra di spostamento sinistra fare clic su **topologia**e quindi su **stato**.
4. Nella pagina Stato ordinare o cercare l'elenco in base alle esigenze per trovare il computer in cui è in esecuzione il servizio che si vuole avviare o arrestare e quindi fare clic su di esso.
5. Fare clic su **Proprietà**.
6. Ordinare l'elenco dei servizi, se necessario, e fare clic sul servizio che si vuole avviare o arrestare.
7. Fare clic su **azione**.
8. Fare clic su **Avvia servizio** o **Interrompi servizio**.
9. Fare clic su **Chiudi**.


## <a name="prevent-sessions-for-services"></a>Impedire le sessioni per i servizi

Usare il pannello di controllo di Skype for business per evitare nuove sessioni per tutti i servizi di Skype for Business Server in uso in un computer specifico o per evitare nuove sessioni per un servizio specifico.

### <a name="prevent-new-sessions-for-all--skype-for-business-server-services-on-a-computer"></a>Impedire nuove sessioni per tutti i servizi di Skype for Business Server in un computer

1. Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. .
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Skype for Business Server, vedere [installare e aprire gli strumenti di amministrazione](../../management-tools/install-and-open-administrative-tools.md).
3. Nella barra di spostamento sinistra fare clic su **topologia** e quindi su **stato**.
4. Nella pagina Stato ordinare o cercare l'elenco in base alle esigenze per trovare il computer in cui sono in esecuzione i servizi per cui si vogliono impedire le nuove sessioni e quindi fare clic su di esso.
5. Fare clic su **azione**.
6. Fare clic su **Impedisci nuove sessioni per tutti i servizi**.

### <a name="prevent-new-sessions-for-a-specific-service"></a>Impedire nuove sessioni per un servizio specifico

1. Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. .
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Skype for Business Server, vedere [installare e aprire gli strumenti di amministrazione](../../management-tools/install-and-open-administrative-tools.md).
3. Nella barra di spostamento sinistra fare clic su **topologia**e quindi su **stato**.
4. Fare clic su **Proprietà**.
5. Ordinare l'elenco dei servizi, se necessario, e fare clic sul servizio per cui si vogliono impedire le nuove sessioni.
6. Fare clic su **azione**.
7. Fare clic su **Impedisci nuove sessioni per il servizio**.
8. Fare clic su **Chiudi**.
