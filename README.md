/**
 **************************************************************************
 **                                Chairman                              **
 **************************************************************************
 * @package mod                                                          **
 * @subpackage chairman                                                  **
 * @name Chairman                                                        **
 * @copyright oohoo.biz                                                  **
 * @link http://oohoo.biz                                                **                                           **
 * @author Dustin Durand                                                 **
 * @license                                                              **
 http://www.gnu.org/copyleft/gpl.html GNU GPL v3 or later                **
 **************************************************************************
 **************************************************************************/

/**
 * This jQuery plugin takes a multiselect html item, and converts it into an
 * multipane exclusive chooser. All options in the multi-select element are
 * considered selected, and can be organized into different exclusive values
 * (or group values) as determined by the value present in the optgroup tag.
 * 
 * The UNIQUE value of each option(has to be unique), is used as an identifier
 * which will be the position in the array where the group value will be returned.
 * For example if an option, with the value = 3, is in an optgroup/pane with value 1 - the submission will be:
 * 
 * [multipane_transfer] => Array
        (
            [3] => 1
        );
 * 
 * Full Example:
 * NOTE: In group 3 the second option doesn't have an value - a plugin generated id is used. 
<form name="oohoo" action="/exmaple.php">
    <select multiple name="multipane_transfer" id="multipane_transfer">
        <optgroup value="1" label="Swedish Car">
            <option value="1">A</option>
            <option value="2">B</option>
        </optgroup>
        <optgroup value="2" label="German Car">
            <option value="A">Mercedes</option>
            <option value="B">Audi</option>
        </optgroup>
        <optgroup value="3" label="Dustin's Car">
            <option value="C">Bike</option>
            <option>Wheel On A Stick</option>
        </optgroup>
        <optgroup value="4" label="Dustin's Cars2"/>
    </select>
<input type="submit" value="Submit">
</form>
 
$_REQUEST:
Array
(
    [multipane_transfer] => Array
        (
            [mpt_5] => 3
            [C] => 3
            [B] => 2
            [A] => 2
            [2] => 1
            [1] => 1
        )
)

Note: Undefined options values(used for unique submission ids) will use a unique id generated in the plugin.
 
 * In this case there are three exclusive groups that each member can be sorted under.
 * They are either a Swedish car, German Car, or Dustin's Car. All options will be submitted
 * with a single value of either 1,2 or 3.
 * 
 * Labels are taken from the optgroups for display labels
 * 
 * Panes can be added dynamically.
 * 
 * Generate by:
 * $("#multipane_transfer").multipanetransfer();
 * 
 * or
 * 
 * $("#multipane_transfer").multipanetransfer({height: '200px'});
 * 
 * 
 */
