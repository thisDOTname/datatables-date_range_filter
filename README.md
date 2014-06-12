dt-date_range_filter
====================

This script can be used along with Datatables jQuery plug-in to filter any date column based on a date-range

<b>Overview:</b>

This function can be used to filter any datatables column with date values. You can select the range by using two date-pickers to get the min and max values. You might have to change the function a bit to make it work for different date formats. By default, the function will filter the datatable's third column(adata[2])which has date in format mm/dd/yyyy


<b>Usage:</b>

A basic example to show the usage of this function:


	$(document).ready(function(){
	        $(function() {
	            $( "#min" ).datepicker();
	        });
			 
	        $(function() {
	            $( "#max" ).datepicker();
	        });
	        
	        var oTable=$('#example').dataTable();
	                
	        /* Add event listeners to the two date-range filtering inputs */
					
		$('#min').change( function() { oTable.fnDraw(); } );
	        $('#max').change( function() { oTable.fnDraw(); } );
    	});
    


'#min' and '#max' represent the two date-range pickers which will create the date-range to filter the table on.
    
By adding "change" event listeners to the two date-range pickers we are redrawing the datatable to show the filtered results everytime the dates in the date-ranger pickes change 


<b>Further Customization for different date formats:</b>

In the daterangefilter.js, 

i)  lines 28,29 and 30 are used to set the date separators for the date ranges and the column data.

ii) In lines 32, 33 and 34, we are creating timestamps for all dates. The default date-format is (mm/dd/yyyy). Depending upon the date format, you might need to change the order of parameters in the Date() function. 
