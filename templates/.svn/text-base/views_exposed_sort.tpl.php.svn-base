<?php 
/**
 * @file views exposed sort buttons
 * 
 * shows links for current view's exposed sort fields.
 * 
 * Variables:
 * $view: The current view object in pre_render state.
 * $title: The title for the sort links.
 * 
 */

?>
 <?php if (!empty($view->args['sort_fields'])): ?>
	  <div class="view-advanced-search-sort-options">
	    <h3 class="sort-options-title"><?php print $title;?></h3>
	    <ul class="inner sort-options-list">
	    <?php foreach($view->args['sort_fields'] as $f => $field): ?>
	        <?php 
	          if(!empty($_GET['sort']) && $_GET['sort'] == $field['alias']
	            && isset($_GET['dir']) && $_GET['dir'] == 'ASC') {
	            $dir = 'DESC';
	          }
	          else{
	            $dir = 'ASC';
	          }
	        ?>
	      <li class="sort-options views-sort-link-<?php 
	      echo strtolower($dir)." ";
	      echo ($_GET['sort'] == $field['alias']?'views-sort-current-sort ':'');?>" >
	        <?php
	          if($field['alias'] == 'field_date_published_value')   {
              $label = 'Date';
            }
            else {  
              $label = $field['label'];
            }
            //Put the parameters in $qsa
            $qsa = $_GET;
            unset($qsa['q']);
            $qsa = array_merge($qsa,array(
	                'sort' => $field['alias'],
	                'dir' => $dir
	              ));
            
            echo l(ucwords($label), urldecode($_GET['q']),array(
	              'query' => $qsa,
	              'attributes' => array(
	                'class' => 'views-sort-link-'.strtolower($dir),
	              ),
	             ));
	        
	        ?>
	      </li>
	    <?php endforeach;?>
	    </ul>
	  </div>
	<?php endif;?>