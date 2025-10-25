<!doctype html>
<ul>
<li>HTML, CSS y JavaScript en un solo archivo.</li>
<li>Formulario que valida y muestra los datos ingresados.</li>
<li>Instrucciones para levantarlo localmente usando solo el archivo.</li>
</ul>


<h3>Prueba local</h3>
<p>Solo abre <strong>index.html</strong> en tu navegador (doble clic). Si quieres, usa un servidor local como <code>Live Server</code> en VS Code para ver cambios automáticamente.</p>


<h3>Snippet de uso (comandos git)</h3>
<pre>git init
git add index.html
git commit -m "primer commit"
git branch -M main
git remote add origin https://github.com/TU_USUARIO/TU_REPO.git
git push -u origin main</pre>
</div>


<aside class="box">
<h3>Demo rápida</h3>
<p style="margin-top:0;color:var(--muted)">Rellena el formulario y verás los datos procesados por JavaScript.</p>


<label for="name">Nombre</label>
<input id="name" type="text" placeholder="Tu nombre" />


<label for="message">Mensaje</label>
<textarea id="message" rows="4" placeholder="Escribe algo..."></textarea>


<button id="send">Enviar</button>


<div id="result" style="margin-top:.75rem;background:rgba(0,0,0,0.25);padding:.5rem;border-radius:8px;min-height:56px">Aquí aparecerá el resultado.</div>


<footer>Listo para GitHub → Render</footer>
</aside>
</section>


<section style="margin-top:1.25rem" class="box">
<h3>Código importante</h3>
<p style="color:var(--muted)">Este archivo incluye CSS y JavaScript embebidos. Puedes separarlos en archivos distintos si prefieres.</p>
<pre>&lt;!-- Guarda como index.html y súbelo al repo --&gt;</pre>
</section>
</main>


<script>
// Lógica simple para el formulario
document.getElementById('send').addEventListener('click', function(){
const name = document.getElementById('name').value.trim();
const msg = document.getElementById('message').value.trim();
const result = document.getElementById('result');


if(!name){
result.innerText = 'Por favor ingresa tu nombre.';
return;
}
if(!msg){
result.innerText = 'Por favor escribe un mensaje.';
return;
}


// Mostrar datos y un pequeño "badge"
result.innerHTML = `
<strong>¡Mensaje enviado!</strong>
<div style="margin-top:.5rem">Nombre: ${escapeHtml(name)}<br>Mensaje: ${escapeHtml(msg)}</div>
`;


// Limpiar campos
document.getElementById('name').value = '';
document.getElementById('message').value = '';
});


function escapeHtml(str){
return str.replace(/[&<>"']/g, function(m){
return ({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":"&#39;"})[m];
});
}
</script>
</body>
</html>
