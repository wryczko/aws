<h1>Zadania do szkolenia</h1>
<a href="https://console.aws.amazon.com">Link do AWS jako root account</a><br>
<a href="https://666786091374.signin.aws.amazon.com/console">Link do "subdomeny" AWS (dla użytkowników stworzonych przez roota)</a>
<h2>Zadanie 1 - Pierwsza usługa - maszyna wirtualna</h2>
<ol>
	<li>Zaloguj się do AWS Console (użyj linku powyżej)</li>
	<li>Przełącz się na region Ireland (prawy górny róg)</li>
	<li>Z listy usług AWS wybierz EC2 (sekcja "Compute")</li>
	<li>Wybierz „Instances” lub "Running instances", a następnie „Launch Instance”</li>
	<li>Dobierz konfigurację
		<ul>
			<li>Step 1: Choose an Amazon Machine Image (AMI): "Windows Server 2012 R2 Base" (piąta od góry)
				<ul>
					<li>Znajdź "Windows Server 2012 R2 Base" (piąty obraz od góry)</li>
					<li>Kliknij niebieski przycisk "Select"</li>
				</ul>
			</li>
			<li>Step 2: Choose an Instance Type
				<ul>
					<li>Znajdź i zaznacz typ/moc instancji "m4.large" (szósta od góry)</li>
					<li>Kliknij szary przycisk "Next: Configure Instance Details"</li>
				</ul>
			</li>
			<li>Step 3: Configure Instance Details
				<ul>
					<li>Zostaw wszystko domyślnie</li>
					<li>Kliknij szary przycisk "Next: Add Storage"</li>
				</ul>
			</li>
			<li>Step 4: Add Storage
				<ul>
					<li>Podaj rozmiar domyślnej partycji (min 30GB)</li>
					<li>Kliknij szary przycisk "Next: Tag Instance"</li>
				</ul>
			</li>
			<li>Step 5: Tag Instance
				<ul>
					<li>W polu "value" podaj nazwę swojej maszyny (będzie potrzebna do indentyfikacji na liście)</li>
					<li>Kliknij szary przycisk "Next: Configure Security Group"</li>
				</ul>
			</li>
			<li>Step 6: Configure Security Group
				<ul>
					<li>Wybierz "Select an existing security group"</li>
					<li>Wybierz Security Group "default"</li>
					<li>Sprawdź czy ma ona otwarty port 3389</li>
					<li>Kliknij niebieski przycisk "Review and Launch"</li>
				</ul>
			</li>
			<li>Step 7: Review Instance Launch
				<ul>
					<li>Sprawdź wprowadzoną konfigurację</li>
					<li>Kliknij niebieski przycisk "Launch" (prawy dolny róg)</li>
				</ul>
			</li>
		</ul>
	</li>
	<li>Select an existing key pair or create a new pair
		<ul>
			<li>Wybierz "Create a new key pair"</li>
			<li>Dowolnie nazwij klucz</li>
			<li>Kliknij szary przycisk "Create"</li>
			<li>Zauważ, że został pobrany plik pem z kluczem</li>
		</ul>
	</li>
	<li>Kliknij niebieski przycisk "Launch Instances"</li>
	<li>Przejdź do listy instancji np. klikając w niebieski przycisk "View Instances"</li>
	<li>Zaloguj się do swojej maszyny wirtualnej
		<ul>
			<li>Znajdź i zaznacz swoją maszynę wirtualną</li>
			<li>Kliknij szary przycisk „Connect” (nad listą instancji)</li>
			<li>Pobierz plik RDP klikając w szary przycisk "Download Remote Desktop File"</li>
			<li>Pobierz hasło
				<ul>
					<li>Kliknij w szary przycisk "Get Password"</li>
					<li>Poczekaj aż odblokuje się możliwość pobrania hasła (2-3 min)</li>
					<li>Kliknij w przycisk "Choose file"</li>
					<li>Znajdź i wybierz uprzednio pobrany plik/klucz</li>
					<li>Kliknij w szary przycisk "Decrypt Password"</li>
					<li>Skopiuj hasło</li>
					<li>Zamknij okno klikając w niebieski przycisk "Close"</li>
				</ul>
			</li>
			<li>Użyj pobranego pliku RDP i hasła do zalogowania się na maszynę wirtualną</li>
			<li>Używaj maszyny wirtualnej w dowolnym celu</li>
		</ul>
	</li>
</ol>
<h2>ZADANIE 2 – SKALOWANIE W GÓRĘ</h2>
<ol>
	<li>Zaalokuj nowy adres publiczny (EIP)
		<ul>
			<li>Z listy usług AWS wybierz EC2 (lewy górny róg)</li>
			<li>Z panelu po lewej stronie wybierz "Elastic IPs" (zakładka "NETWORK & SECURITY")</li>
			<li>Kliknij niebieski przycisk "Allocate New Address"</li>
			<li>Potwierdź zamiar klikając niebieski przycisk "Yes, Allocate"</li>
			<li>Zamknij okno klikając niebieski przycisk "Close"</li>
		</ul>
	</li>
	<li>Podepnij EIP do istniejącej instancji
		<ul>
			<li>Zaznacz nowoutworzony EIP</li>
			<li>Kliknij szary przycisk "Actions" (nad listą) lub kliknij prawym przyciskiem myszy na EIP</li>
			<li>Wybierz opcję "Associate Address"</li>
			<li>Kliknij w textbox "Instance", znajdź i wybierz swoją instancję</li>
			<li>Kliknij niebieski przycisk "Associate"</li>
		</ul>
	</li>
	<li>Sprawdź wydajność swojej maszyny wirtualnej
		<ul>
			<li>Pobierz plik "benchmark.exe" z "\\morpheus\pub-Transfer\w\wryczko\FP_AWS_Training\benchmark.exe"
			<li>Zaloguj się do maszyny wirtualnej (opis w zadaniu 1)</li>
			<li>Skopiuj i odpal plik benchmark.exe z liczbą iteracji (domyślnie 10)</li>
			<li>Na maszynie m4.large test trwa niecałą minutę</li>
			<li>Zapisz czas wykonania programu</li>
		</ul>
	</li>
	<li>Utwórz obraz maszyny wirtualnej (AMI)
		<ul>
			<li>Przejdź do listy instancji</li>
			<li>Zaznacz swoją instancję</li>
			<li>Kliknij szary przycisk "Actions" (nad listą) lub kliknij prawym przyciskiem myszy na instancję</li>
			<li>Wybierz opcję "Image"->"Create Image"</li>
			<li>W polu "Instance name" wpisz dowolną nazwę obrazu</li>
			<li>Kliknij niebieski przycisk "Create Image"</li>
			<li>Zamknij okno klikając niebieski przycisk "Close"</li>
			<li>Przejdź do listy utworzonych obrazów klikając na panelu z lewej strony "AMIs" (zakładka "IMAGES")</li>
			<li>Poczekaj aż obraz będzie gotowy (3-4 min)</li>
		</ul>
	</li>
	<li>Utwórz maszynę wirtualną z obrazu AMI
		<ul>
			<li>Przejdź do listy instancji</li>
			<li>Kliknij „Launch Instance”</li>
			<li>Step 1: Choose an Amazon Machine Image (AMI)
				<ul>
					<li>Wybierz z lewego panelu "My AMIs"</li>
					<li>Znajdź swój nowoutworzony obraz</li>
					<li>Kliknij niebieski przycisk "Select"</li>
				</ul>
			</li>
			<li>Step 2: Choose an Instance Type
				<ul>
					<li>Wybierz mocniejszą maszynę (np. m4.4xlarge)</li>
				</ul>
			</li>
			<li>Reszta kroków jak w zadaniu 1</li>
			<li>Tym razem nie musisz tworzyć nowego pliku-klucza. Możesz wybrać istniejący.</li>
		</ul>
	</li>
	<li>Zacznij sprawdzać dostępność maszyny wirtualnej
		<ul>
			<li>Sprawdź adres IP (EIP)</li>
			<li>Na lokalnym komputerze odpal command line</li>
			<li>Użyj narzędzia ping: "ping {IP} -t"</li>
			<li>Nie zamykaj konsoli do końca zadania</li>
		</ul>
	</li>
	<li>Przełącz EIP (publiczny IP) między maszynami wirtualnymi
		<ul>
			<li>Przejdź do listy EIP</li>
			<li>Kliknij szary przycisk "Actions" (nad listą) lub kliknij prawym przyciskiem myszy na EIP</li>
			<li>Wybierz opcję "Associate Address"</li>
			<li>Kliknij w textbox "Instance", znajdź i wybierz swoją nową (mocniejszą) instancję</li>
			<li>Zaznacz opcje "Reassociation"</li>
			<li>Kliknij niebieski przycisk "Associate"</li>
		</ul>
	</li>
	<li>Zaobserwuj w command line, czy użytkownik odczuje "skalowanie"</li>
	<li>Sprawdź wydajność swojej nowej (mocniejszej) maszyny wirtualnej
		<ul>
			<li>Zaloguj się do maszyny przez RDP (jeżeli nie tworzyłeś nowego klucza, to hasło jest takie samo jak na starej maszynie)</li>
			<li>Zauważ, że plik "benchmark.exe" już się tam znajduje</li>
			<li>Odpal plik benchmark.exe z liczbą iteracji jak na pierwszej maszynie (domyślnie 10)</li>
			<li>Zapisz czas wykonania programu</li>
		</ul>
	</li>
	<li>Porównaj wyniki obu testów maszyn wirtualnych (słabszej i mocniejszej)</li>
	<li>Usuń słabszą maszynę (posprzątaj)
		<ul>
			<li>Przejdź do listy instancji</li>
			<li>Zaznacz swoją starą (słabszą) instancję</li>
			<li>Kliknij szary przycisk "Actions" (nad listą) lub kliknij prawym przyciskiem myszy na instancję</li>
			<li>Wybierz opcję "Instance State"->"Terminate"</li>
			<li>Potwierdź działanie klikając niebieski przycisk "Yes, terminate"</li>
		</ul>
	</li>
</ol>
<h2>ZADANIE 3 – ZAŁADUJ I UDOSTĘPNIJ PLIK</h2>
<ol>
	<li>Pobierz pliki testowe
		<ul>
			<li>Wejdź na \\morpheus\pub-Transfer\w\wryczko\FP_AWS_Training</li>
			<li>Skopiuj na lokalny komputer plik test10MB.dat</li>
			<li>Skopiuj na lokalny komputer plik downloader.exe</li>
		</ul>
	</li>
	<li>Przygotuj usługę S3
		<ul>
			<li>Z listy usług AWS wybierz S3 (kategoria "Storage & Content Delivery")</li>
			<li>Kliknij w niebieski przycisk "Create Bucket" w lewym górnym rogu</li>
			<li>W polu "Bucket Name" podaj unikalną (na skalę AWS) nazwę bucketa</li>
			<li>Wybierz jakiś odległy region (np. Sydney, Tokyo)</li>
			<li>Kliknij w niebieski przycisk "Create"</li>
		</ul>
	</li>
	<li>Wgraj plik testowy do usługi S3 i udostępnij
		<ul>
			<li>Otwórz bucket (kliknij w jego nazwę na liście)</li>
			<li>Kliknij w niebieski przycisk "Upload" w lewym górnym rogu</li>
			<li>Kilknij w przycisk "Add files" (zielona ikona z plusem)</li>
			<li>Znajdź i wybierz pobrany plik test10MB.dat</li>
			<li>Kliknij szary przycisk "Start Upload" w prawym dolnym rogu</li>
			<li>Poczekaj aż plik zostanie załadowany do usługi S3</li>
			<li>Kliknij prawym przyciskiem myszy na plik i wybierz opcję "Make Public"</li>
		</ul>
	</li>
	<li>Przeprowadź test czasu odpowiedzi
		<ul>			
			<li>Kliknij lewym przyciskiem myszy w plik w bucketcie</li>
			<li>Wybierz szarą zakładkę 'Properties' w prawy górnym rogu</li>
			<li>Znajdź i skopiuj link do pliku</li>
			<li>Wydziel z linku hosta (np. s3.eu-central-1.amazonaws.com)</li>
			<li>Otwórz 'CMD'</li>
			<li>Odpytaj host bucketa narzędziem ping (np. ping s3-website-eu-west-1.amazonaws.com)</li>
			<li>Zapisz czas odpowiedzi</li>
		</ul>
	</li>
	<li>Przeprowadź test prędkości pobierania
		<ul>
			<li>Przygotuj link do pliku</li>
			<li>Pobierz kilka razy plik za pomocą downloadera (np. downloader.exe http://s3-eu-west-1.amazonaws.com/fptrainingaws/FPTrainingAWS.zip)</li>
			<li>Zapisz średni czas pobierania</li>
		</ul>
	</li>
</ol>
<h2>ZADANIE 4 – ROZPROSZ PLIK PO CAŁYM ŚWIECIE</h2>
<ol>
	<li>Przygotuj usługę CloudFront
		<ul>
			<li>Wybierz usługę CloudFront (kategoria "Storage & Content Delivery")</li>
			<li>Kliknij w niebieski przycisk „Create Distribution” w lewym górnym rogu</li>
			<li>Kliknij w niebieski przycisk "Get Started" pod wersją „Web”</li>
			<li>W polu "Origin Domain Name" wybierz bucket S3 (utworzony w poprzednim zadaniu)</li>
			<li>Resztę konfiguracji zostaw domyślną</li>
			<li>Kliknij w niebieski przycisk „Create Distribution” w prawym dolnym rogu</li>	
		</ul>
	</li>
	<li>Odczekaj minimum 15 minut (przerwa na kawę)</li>
	<li>Przeprowadź test czasu odpowiedzi
		<ul>
			<li>Znajdź i skopiuj adres hosta CloudFront ("Domain Name")</li>
			<li>Otwórz 'CMD'</li>
			<li>Odpytaj host CloudFronta narzędziem ping (np. ping d30wp07u6aouly.cloudfront.net)</li>
			<li>Zapisz czas odpowiedzi</li>
		</ul>
	</li>
	<li>Przeprowadź test prędkości pobierania
		<ul>
			<li>Doklei do adresu hosta CloudFronta nazwę pliku (bez nazwy bucketa S3)</li>
			<li>Pobierz kilka razy plik za pomocą downloadera (np. downloader.exe http://d30wp07u6aouly.cloudfront.net/FPTrainingAWS.zip)</li>
			<li>Zapisz średni czas pobierania</li>
		</ul>
	</li>
</ol>
<h2>ZADANIE 5 – SECURITY GROUPS - FIREWALL</h2>
<ol>
	<li>Utwórz Security Group
		<ul>
			<li>Przejdź do usługi EC2</li>
			<li>Z panelu po lewej stronie wybierz "Security Groups" (zakładka "NETWORK & SECURITY")</li>
			<li>Kliknij niebieski przycisk "Create Security Group"</li>
			<li>Nadaj nazwę oraz opis</li>
			<li>Kliknij niebieski przycisk "Create"</li>
		</ul>
	</li>
	<li>Zacznij wysyłać pakiety ICMP do EC2 (ping -t)</li>
	<li>Przypisz nowe Security Group do EC2
		<ul>
			<li>Przejdź do listy instancji</li>
			<li>Zaznacz swoją (jedyną) instancję</li>
			<li>Kliknij szary przycisk "Actions" (nad listą) lub kliknij prawym przyciskiem myszy na instancję</li>
			<li>Wybierz opcję "Networking"->"Change Security Groups"</li>
			<li>Odznacz domyślne Security Group</li>
			<li>Zaznacz nowoutworzone Security Group</li>
			<li>Kliknij niebieski przycisk "Assign Security Groups"</li>
		</ul>
	</li>
	<li>Sprawdź czy przypisanie nowych zasad przepuszcza pakiety ICMP (propagacja odebrania dostępu w SG trwa 5 min, restart vm i nadanie praw daje natychmiastowy efekt)</li>
	<li>Skonfiguruj Security Group
		<ul>
			<li>Znajdź i zaznacz nowoutworzone Security Group</li>
			<li>Kliknij szary przycisk "Actions" lub kliknij prawym przyciskiem myszyny na Security Group</li>
			<li>Wybierz opcję "Edit inbound rules" lub kliknij "Edit" w zakładce "Inbound" w panelu na dole</li>
			<li>Wybierz Type "All ICMP"</li>
			<li>Wybierz Source "My IP"</li>
			<li>Kliknij niebieski przycisk "Save"</li>
		</ul>
	</li>
	<li>Sprawdź czy przypisanie nowych zasad przepuszcza pakiety ICMP</li>
</ol>
<h2>ZADANIE 6 – SKALOWANIE HORYZONTALNE (WSZERZ)</h2>
<ol>
	<li>Przygotuj Security Groupy
		<ul>
			<li>Stwórz Security Group dla Load Balancera z otwarym portem 80 dla wszystkich</li>
			<li>Stwórz Security Group dla EC2 z otwartym portem 80 tylko dla Security Groupy Load Balancera z poprzedniego kroku</li>
		</ul>
	</li>
	<li>Przygotuj dwa EC2
		<ul>
			<li>Stwórz dwie EC2 wykorzystując obraz AMI „SimpleELBImage” (region Ireland) lub „ELBExample” (region Frankfurt)</li>
			<li>Podczas tworzenia EC2 wybierz nowoutworzone Security Group (z punktu 1)</li>
		</ul>
	</li>
	<li>Przygotuj Load Balancer
		<ul>
			<li>Wybierz usługę EC2</li>
			<li>Z panelu po lewej wybierz "Load balancers" (zakładka "Load balancing")</li>
			<li>Kliknij w niebieski przycisk "Create Load Balancer" w lewym górnym rogu</li>
				<ol>
					<li>Step 1: Define Load Balancer</li>
					<ul>
						<li>W polu "Load Balancer name" wpisz wymaganą nazwę</li>
						<li>Kliknij w szary przycisk "Next: Assign Security Groups" w prawym dolnym rogu</li>
					</ul>
					<li>Step 2: Assign Security Groups</li>
					<ul>
						<li>Wybierz opcję "Select an existing security group"</li>
						<li>Zaznacz nowoutworzone Security Group z punktu 1</li>
						<li>Kliknij w szary przycisk "Next: Configure Security Settings" w prawym dolnym rogu</li>
					</ul>
					<li>Step 3: Configure Security Settings</li>
					<ul>
						<li>Pomiń ten krok na potrzeby szkolenia</li>
						<li>Kliknij w szary przycisk "Next: Configure Health Check" w prawym dolnym rogu</li>
					</ul>
					<li>Step 4: Configure Health Check</li>
					<ul>
						<li>W polu "Ping Path" wpisz adres głównej strony, czyli w naszym przypdku slash "/"</li>
						<li>W polu "Health Check Interval" wpisz "10"</li>
						<li>W polu "Healthy Threshold" wybierz "2"</li>
						<li>Kliknij w szary przycisk "Next: Add EC2 Instances" w prawym dolnym rogu</li>
					</ul>
					<li>Step 5: Add EC2 Instances</li>
					<ul>
						<li>Z listy dostępnych EC2 wybierz te dwie utworzone w punkcie 2</li>
						<li>Kliknij w szary przycisk "Next: Add Tags" w prawym dolnym rogu</li>
					</ul>
					<li>Step 6: Add Tags</li>
					<ul>
						<li>(opcjonalnie) Analogicznie jak podczas tworzenia EC2 należy podać np. nazwę instacji</li>
						<li>Kliknij w niebieski przycisk "Review and Create" w prawym dolnym rogu</li>
					</ul>
					<li>Step 7: Review</li>
					<ul>
						<li>(opcjonalnie) Przejrzyj podsumowanie konfiguracji Load Balancera</li>
						<li>Kliknij w niebieski przycisk "Create" w prawym dolnym rogu</li>
					</ul>
				</ol>
			</li>
		</ul>
	</li>
	<li>Poczekaj chwilę, aż Load Balancer zarejestruje sobie instancje EC2</li>
	<li>Przetestuj Load Balancer
		<ul>
			<li>Skorzystaj z usługi (otwórz w przeglądarce) korzystając z adresu Load Balancera</li>
			<li>Odśwież kilka razy i zauważ zmieniające się adresy IP</li>
		</ul>
	</li>
</ol>
