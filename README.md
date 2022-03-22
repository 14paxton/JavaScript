 

· CDN Fallback

       <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.3/jquery.min.js"></script>
       <script>!window.jQuery && document.write('<script src="/js/libs/jquery-1.11.1.min.js"><\/script>')</script>

 

·Monitor Events-https://stackoverflow.com/questions/10213703/how-do-i-view-events-fired-on-an-element-in-chrome-devtools

     o   You can use monitorEvents function.

      o   Just inspect your element (right mouse click → Inspect on visible element or go to Elements tab in Chrome Developer Tools and select wanted                    element) then go to Console tab and write:

   §  monitorEvents($0)
      o   Now when you move mouse over this element, focus or click it, the name of the fired event will be displayed with its data.

       o   To stop getting this data just write this to console:

   §  unmonitorEvents($0)
        o   $0 is just the last DOM element selected by Chrome Developer Tools. You can pass any other DOM object there (for example result of         getElementById or querySelector).

        o   You can also specify event "type" as second parameter to narrow monitored events to some predefined set. For example:

   §  monitorEvents(document.body, 'mouse')
        o    

              ·       Appending HTML to an element

               $.each(arr, function() {

                       appendString += "<div>" + this + "</div>";

                                       });

                    $('#parent').append('<div>' + appendString + '</div>');  

             ·       Document Ready

          $(function(){

            Console.log(“ready”);

 });

 $(document).ready(function() {

            Console.log(“ready”);

});

·       Slice

o   selectedItems.slice(50)

§  select everything after the 50th item in the list

·       select checkbox items

o   var selectedItems =$('input[type="checkbox"]:checked', '#card');

o   selectedItems.prop('checked', false);  “uncheck them”

 

·       use “arguments” keyword in function to get arguments passed or available

 

·       Using on

$(“selector”).on(“click”, myHandlerFunction);

 

 

Connect multiple events

$(“selector”).on({

“click”: clickFunction,

“hover: hoverFunction

});

 

 

 

·       Custom Events

Car.lightTurnedGreen = function(){…}

$(trafficLight).on(“green”, car.lightTurnedGreen);

$(trafficLight).trigger(“green”);

 

 

·       Custom Bindings

·       /*   //declare event to run when div is visible
   function isVisible(){
       alert("works")

   }

   //hookup the event
   $('#results-table').bind('isVisible', isVisible);

   //show div and trigger custom event in callback when div is visible
   $('#results-table').show('slow', function(){
       $(this).trigger('isVisible');
   });*/


  /* $('#results-table').show('slow',function(){
       alert('example')
   });

 

 

 

·       Sending form data with a file input via jquery ajax

		<a href="https://gist.github.com/14paxton/eeeb29357613698bd877eb35dcf0ad89">SendFormDataWithFileInput</a>
 

 

 

Hide/Show Element

·       jquery $(‘element’).hide();    $(‘element’).show()   also $(‘element’).toggle()

o   show = elem.style.display = 'block';  hide = elem.style.display = 'none';

·        

·       element.style.display = 'none';           // Hide
·       element.style.display = 'block';          // Show
·       element.style.display = 'inline';         // Show
·       element.style.display = 'inline-block';   // Show
·       element.style.visibility = 'hidden';      // Hide
·       element.style.visibility = 'visible';     // Show
·       element.setAttribute("hidden", true); //hide
·       element.toggle()
 

GET INPUT ELEMENTS

 

       ·       $("input[type='radio'][name='scheduleType']:not(:checked)").attr(
                    "disabled", true);

        ·      Get by text jQuery( ":contains(text)" )

         ·      document.querySelector("input[name=rate]:checked").value

         ·       id like =  document.querySelector('[id^="poll-"]').id;

       ·      check if element exists

          o   (document.body.contains(document.getElementById('test')))
  
o    

 

 

·      GET ATTRibutes

o   document.getElementById('groupsWrapper-'+id).getAttribute('data-saved-assessment-count')

§  .setAttribute()

§  Element.dataset.attributeNameCamelCased

·      http://html5doctor.com/html5-custom-data-attributes/

o   JQUERY = $(selectElement).data('saved-assessment-count',currentTotalResultCount);

§  If using .data() to modify, you need to retrieve by .data() so new value will be reflected

 

You Can pass arguments to functions that do no accept parameters

·      call arguments in method to see what has been passed

Properties

arguments.callee

Reference to the currently executing function that the arguments belong to.

arguments.caller 

Reference to the function that invoked the currently executing function.

arguments.length

The number of arguments that were passed to the function.

arguments[@@iterator]

Returns a new Array iterator object that contains the values for each index in arguments.

 

 

-       Fn.call  immediately calls a function

-       Fn.apply allows you to pass in an array for parameters

-       Fn.bind will bind parameters to a new function

o   var newFunc = oldFunc.bind({name: ted} , params[])  

 

 

-       async () => { const x = await getUser(‘username’)}

o   async await will wait for promise from async function

 

 

-Get width of element-

            console.log( $('#getwidth').width()/ $('#getwidth').parent().width() * 100);

 

-The reduce() method executes a reducer function (that you provide) on each element of the array, resulting in a single output value

const array1 = [1, 2, 3, 4];

const reducer = (accumulator, currentValue) => accumulator + currentValue;

console.log(array1.reduce(reducer));

 

data.reduce(function (filtered, member) {
  if (member?.id !== orderToRemoveProps?.orderId) {
    filtered.push(member.id);
  }
  return filtered;
}, []);

 

 

 

concat array in place

            groupList.push.apply(groupList, groupElements.toArray());

MAPS

·      modifiedResults.map((result) => [result.id, result.name])

·      resultsNameMap.get(option)

·       

 

 

Sort and filter map

      const filteredResults = new Map(
          selectedResults.map((key) => [
                         key,
                   resultsNameMap.get(key)]))

            const sortedChips = new Map([...filteredResults.entries()].sort((a,b) => customSort(a[1],b[1])))

 


## OBJECTS:

### Sum object values

         const sum = Object.values(getValues(scoreIds)).reduce((a, b) => parseFloat(a) + parseFloat(b), 0);

 

FORM

-set validity

- https://stackoverflow.com/questions/50909019/form-validation-set-custom-validity

- https://developer.mozilla.org/en-US/docs/Web/API/ValidityState

       - e.target.setCustomValidity('invalid');
 

 

Regex

·      regEx.test(string) – tests it exists

·      string.match(regEx) – returns the matches

·      use ( ) in expression to capture a group to select/replace substring or to find something before or behind

·      regEx(string) – can be used to continue to iterate through string, each call will get next match
