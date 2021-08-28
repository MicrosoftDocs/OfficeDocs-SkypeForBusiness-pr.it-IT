---
title: Test dei diritti di topologia dell'amministratore in Skype for Business Server
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
description: Come testare i diritti di topologia in Skype for Business Server
ms.openlocfilehash: 7e1d7b8fe1f2b35cffd63aa8816b36946cdc500f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580540"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a>Test dei diritti di topologia dell'amministratore in Skype for Business Server

|&nbsp; |&nbsp; |
|--|--|
|Pianificazione della verifica|Dopo la distribuzione Skype for Business Server iniziale. Se necessario, se si verificano problemi relativi alle autorizzazioni.|
|Strumento di testing|Windows PowerShell|
|Autorizzazioni necessarie|Quando vengono eseguiti localmente Skype for Business Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.<br/><br/>Quando viene eseguito utilizzando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che dispone dell'autorizzazione per eseguire il cmdlet Test-CsSetupPermission. Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, dal prompt dei comandi Windows PowerShell seguente:<br/><br/>Get-CsAdminRole Where-Object \| {$_. Cmdlet -match "Test-CsSetupPermission"}|
|||

## <a name="description"></a>Descrizione

Per impostazione predefinita, solo gli amministratori di dominio possono abilitare una topologia Skype for Business Server e apportare modifiche di grandi dimensioni all'Skype for Business Server aziendale. Questo non sarà un problema, purché gli amministratori di dominio e gli Skype for Business Server amministratori siano uguali. In molte organizzazioni, Skype for Business Server non dispongono di diritti amministrativi per l'intero dominio. Per impostazione predefinita, questo significa che questi amministratori (definiti come membri del gruppo RTCUniversalServerAdmins) non possono apportare modifiche Skype for Business Server topologia. Per concedere ai membri del gruppo RTCUniversalServerAdmins il diritto di apportare modifiche alla topologia, è necessario assegnare le autorizzazioni di Active Directory necessarie utilizzando il cmdlet [Grant-CsSetupPermission.](/powershell/module/skype/Grant-CsSetupPermission)
 
Il cmdlet Test-CsSetupPermission verifica che le autorizzazioni necessarie per installare Skype for Business Server o uno dei relativi componenti siano configurate nel contenitore di Active Directory specificato. Se le autorizzazioni non sono assegnate, è possibile eseguire il cmdlet Grant-CsSetupPermission per concedere ai membri del gruppo RTCUniversalServerAdmins il diritto di installare e abilitare Skype for Business Server.

## <a name="running-the-test"></a>Esecuzione del test

Per determinare se le autorizzazioni di installazione sono assegnate per un contenitore di Active Directory, chiamare il cmdlet Test-CsSetupPermission. Specificare il nome distinto del contenitore da controllare. Ad esempio, questo comando verifica le autorizzazioni di installazione per il contenitore ou=CsServers,dc=litwareinc,dc=com:

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Test-CsSetupPermission.](/powershell/module/skype/Test-CsSetupPermission)

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Se Test-CsSetupPermission che le autorizzazioni necessarie sono già state impostate in un contenitore di Active Directory, il cmdlet restituirà il valore True:

Vero 

Se le autorizzazioni non sono impostate, Test-CsSetupPermission restituirà il valore False. Si noti che questo valore viene in genere racchiuso in molti messaggi di avviso. Ad esempio:

AVVISO: voce di controllo di accesso (ACE) atl-cs-001\RTCUniversalServerAdmins; Consenti; ExtendedRight; Nessuno; Nessuno; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2 

AVVISO: le voci di controllo di accesso (ACE) sull'oggetto "CN=Computers,DC=litwareinc,DC=com" non sono pronte. 

Falso 

AVVISO: l'elaborazione "Test-CsSetupPermission" è stata completata con avvisi. Durante questa esecuzione sono stati registrati avvisi di tipo "2". 

AVVISO: i risultati dettagliati sono disponibili in "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html". 

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Anche se esistono rare eccezioni, se Test-CsSetupPermission ha esito negativo, in genere significa che le autorizzazioni di installazione non vengono assegnate per il contenitore di Active Directory specificato. Tali autorizzazioni possono essere assegnate utilizzando il cmdlet Grant-CsSetupPermission. Ad esempio, questo comando concede le autorizzazioni di installazione al contenitore Computer nel dominio litwareinc.com:

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Test-CsSetupPermission.](/powershell/module/skype/Test-CsSetupPermission)