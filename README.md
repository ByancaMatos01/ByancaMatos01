## Bem-vindo(a) ao perfil da Byanca Matos  😁

 <div>
   <a href="https://github.com/ByancaMatos01">
   <img height="180em" src="https://github-readme-stats.vercel.app/api?username=ByancaMatos01&show_icons=true&theme=tokyonight&include_all_commits=true&count_private=true"/>
   <img height="180em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=ByancaMatos01&layout=compact&langs_count=6&theme=tokyonight"/>
<div>    
Frontend  
<div align="center">    
<img style="margin: 10px" src="https://profilinator.rishav.dev/skills-assets/html5-original-wordmark.svg" alt="HTML5" height="50" />  
<img style="margin: 10px" src="https://profilinator.rishav.dev/skills-assets/css3-original-wordmark.svg" alt="CSS3" height="50" />  
<img style="margin: 10px" src="https://profilinator.rishav.dev/skills-assets/javascript-original.svg" alt="JavaScript" height="40" />
 <img style="margin: 10px" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vscode/vscode-original.svg" alt="VS-code" height="50" />
  <img style="margin: 10px" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/bootstrap/bootstrap-original.svg" alt="bootstrap5" height="50"/>
</div>
    
 <div>
 Backend  
<div align="center">    
<img style="margin: 10px" src="https://profilinator.rishav.dev/skills-assets/php-original.svg" alt="PHP" height="50" />   
<img style="margin: 10px" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/java/java-original-wordmark.svg" alt="Java" height="50" />
 <img style="margin: 10px"  src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/c/c-original.svg" alt="C"   height="50"/> 
</div>
 DevOps  
<div align="center">  
<img style="margin: 10px" src="https://profilinator.rishav.dev/skills-assets/git-scm-icon.svg" alt="Git" height="50" />  
<img style="margin: 10px" src="https://profilinator.rishav.dev/skills-assets/gitlab.svg" alt="GitLab" height="50" />  
 <img style="margin: 10px" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original-wordmark.svg" alt="MSQL" height="50"/>
</div>  
<br/>    
  ### Para entrar em contato redes sociais abaixo !
 
<div> 
 <a href="https://discord.com/channels/970867783967584286/970867783967584288" target="_blank"><img src="https://img.shields.io/badge/Discord-7289DA?style=for-the-badge&logo=discord&logoColor=white" target="_blank"></a> 
  <a href = " mailto:byancathmatos@gmail.com"><img src="https://img.shields.io/badge/-Gmail-%23333?style=for-the-badge&logo=gmail&logoColor=white" target="_blank"></a>
  <a href="https://www.linkedin.com/in/byanca-matos-29204b1bb/" target="_blank"><img src="https://img.shields.io/badge/-LinkedIn-%230077B5?style=for-the-badge&logo=linkedin&logoColor=white" target="_blank"></a> 
 
<?php

	function get_num_visitas(){
		//conectar
		$link = mysql_connect('localhost', 'root', '');
		if (!$link) {
			die('Não foi possível conectar: ' . mysql_error());
		}
		
		mysql_select_db("contador");
		$query = "SELECT total " .
				 "FROM `visitas` " .
				 "ORDER BY total ASC LIMIT 1";
		$result = mysql_query($query);
		if (!$result) {
			$message  = 'Invalid query: ' . mysql_error() . "\n";
			$message .= 'Whole query: ' . $query;
			die($message);
		}
		if (mysql_num_rows($result) == 0) {
			echo "No rows found, nothing to print so am exiting";
			exit;
		}
		$row = mysql_fetch_array($result);
		mysql_close($link);
		return $row["total"];
		//fazer consulta
		//retornar total
	}

	function imprime_visitas($contador){
		return "<h1>" . $contador . "</h1>";
	}
	
	function contar_visita(){
		//conectar
		$link = mysql_connect('localhost', 'root', '');
		if (!$link) {
			die('Não foi possível conectar: ' . mysql_error());
		}
		
		mysql_select_db("contador");
		$query = "UPDATE `visitas` " .
				 "SET total = total + 1";
		$result = mysql_query($query);
		if (!$result) {
			$message  = 'Invalid query: ' . mysql_error() . "\n";
			$message .= 'Whole query: ' . $query;
			die($message);
		}
		mysql_close($link);
	}

	contar_visita();
	$contador = get_num_visitas();
	echo imprime_visitas($contador);

?>


</div>
