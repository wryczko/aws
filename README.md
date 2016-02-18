<h1>Zadania do szkolenia</h1>
<a href="https://666786091374.signin.aws.amazon.com/console">Link do AWS</a>
<h3>FPTrainingUser[1-15]/SilneHasłoFP<h3> 
<h2>Zadanie 1 - PIERWSZA USŁUGA</h2>
<ol>
	<li>Zaloguj się do AWS Console i wybierz usługę EC2</li>
	<li>Wybierz zakładkę „Instances”, a następnie „Launch Instance”</li>
	<li>Dobierz konfigurację
		<ul>
			<li>obraz maszyny (Windows Server 2012 R2 Base)</li>
			<li>rozmiar instancji (np. m4.large)</li>
			<li>(opcjonalnie) przestrzeń dyskową, security group</li>
		</ul>
	</li>
	<li>Wygeneruj klucz prywatny i zapisz na dysku</li>
	<li>Kliknij „Launch instances”</li>
	<li>Znajdź swoją maszynę wirtualną i kliknij „Connect”</li>
	<li>Pobierz plik RDP i hasło wykorzystując klucz prywatny</li>
	<li>Zaloguj się do maszyny przez RDP</li>
</ol>
<h2>ZADANIE 2 – SKALOWANIE W GÓRĘ</h2>
<ol>
	<li>Zaalokuj nowy adres publiczny (EIP)</li>
	<li>Podepnij EIP do istniejącej instancji i sprawdź jej dostępność</li>
	<li>Zmień zawartość dysku (np. utworzyć plik na pulpicie)</li>
	<li>Utwórz obraz istniejącej maszyny wirtualnej (AMI)</li>
	<li>Skonfiguruj nową większą instację EC2 korzystając z nowopowstałego obrazu</li>
	<li>Zaloguj się do maszyny przez RDP (hasło z oryginału)</li>
</ol>