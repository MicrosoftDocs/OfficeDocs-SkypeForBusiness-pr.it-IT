---
title: Test dei diritti di topologia di amministratore in Skype for Business Server
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
description: Come verificare i diritti di topologia in Skype for Business Server
ms.openlocfilehash: de2f5752bdcd9096a47595fd7ffd10a3ab799d9c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030149"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a>Test dei diritti di topologia di amministratore in Skype for Business Server

| | |
|--|--|
|Pianificazione della verifica|Dopo la distribuzione iniziale di Skype for Business Server. Se necessario, se si verificano problemi relativi alle autorizzazioni.|
|Strumento di testing|Windows PowerShell|
|Autorizzazioni necessarie|Quando si esegue localmente usando Skype for Business Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.<br/><br/>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsSetupPermission. Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:<br/><br/>Get-CsAdminRole \| Where-Object {$ _. Cmdlet-match "Test-CsSetupPermission"}|
|||

## <a name="description"></a>Descrizione

Per impostazione predefinita, solo gli amministratori di dominio possono abilitare la topologia di Skype for Business Server e apportare modifiche importanti all'infrastruttura di Skype for Business Server. Non si tratta di un problema a condizione che gli amministratori di dominio e gli amministratori di Skype for Business Server siano identici. In molte organizzazioni, gli amministratori di Skype for Business Server non contengono diritti amministrativi per l'intero dominio. Per impostazione predefinita, questo significa che questi amministratori (definiti come membri del gruppo RTCUniversalServerAdmins) non possono apportare modifiche alla topologia di Skype for Business Server. Per concedere ai membri del gruppo RTCUniversalServerAdmins il diritto di apportare modifiche alla topologia, è necessario assegnare le autorizzazioni di Active Directory necessarie utilizzando il cmdlet [Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) .
 
Il cmdlet Test-CsSetupPermission verifica che le autorizzazioni necessarie per l'installazione di Skype for Business Server o di uno dei suoi componenti siano configurate nel contenitore di Active Directory specificato. Se le autorizzazioni non sono assegnate, è possibile eseguire il cmdlet Grant-CsSetupPermission per assegnare ai membri del gruppo RTCUniversalServerAdmins il diritto di installare e abilitare Skype for Business Server.

## <a name="running-the-test"></a>Esecuzione del test

Per determinare se le autorizzazioni di installazione sono assegnate a un contenitore di Active Directory, chiamare il cmdlet Test-CsSetupPermission. Specificare il nome distinto del contenitore da controllare. Ad esempio, questo comando consente di verificare le autorizzazioni di installazione sul contenitore ou = CsServers, DC = litwareinc, DC = com:

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Se Test-CsSetupPermission determina che le autorizzazioni necessarie sono già state impostate su un contenitore di Active Directory, il cmdlet restituirà il valore true:

True 

Se le autorizzazioni non sono impostate, Test-CsSetupPermission restituirà il valore false. Si noti che questo valore verrà in genere racchiuso in molti messaggi di avviso. Ad esempio:

AVVISO: voce di controllo di accesso (ACE) atl-cs-001\RTCUniversalServerAdmins; Consentire ExtendedRight; Nessuno Nessuno 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2 

AVVISO: le voci di controllo di accesso (ACE) dell'oggetto "CN = Computers, DC = litwareinc, DC = com" non sono pronte. 

False 

AVVISO: l'elaborazione di "Test-CsSetupPermission" è stata completata con gli avvisi. gli avvisi "2" sono stati registrati durante la fase di esecuzione. 

AVVISO: i risultati dettagliati sono disponibili su "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html". 

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Sebbene esistano eccezioni rare, se Test-CsSetupPermission ha esito negativo che in genere significa che le autorizzazioni di installazione non sono assegnate per il contenitore di Active Directory specificato. Tali autorizzazioni possono essere assegnate utilizzando il cmdlet Grant-CsSetupPermission. Ad esempio, questo comando concede le autorizzazioni di installazione al contenitore computer nel dominio litwareinc.com:

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .
