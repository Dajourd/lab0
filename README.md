# lab0
//
//  ViewController.swift
//  LabZero
//
//  Created by Dajour Dixon on 8/23/24.
//

import UIKit

class ViewController: UIViewController {
    
    @IBOutlet weak var Petstepper: UIStepper!
    @IBOutlet weak var Morepetsswitch: UISwitch!
    @IBOutlet weak var FirstnameTextfield: UITextField!
    @IBOutlet weak var LastnameTextfield: UITextField!
    @IBOutlet weak var Yearcontrol: UISegmentedControl!
    @IBOutlet weak var SchoolTextfield: UITextField!
    @IBOutlet weak var NumberofPets: UILabel!
    @IBAction func IntroduceTextfield(_ sender: UIButton) {
        // Lets us choose the title we have selected from the segmented control
               // In our example that is whether it is first, second, third or forth
               let year = Yearcontrol.titleForSegment(at: Yearcontrol.selectedSegmentIndex)
               
               // Creating a constant of type string that holds an introduction. The introduction receives the values from the outlet connections.
               let introduction = "My name is \(FirstnameTextfield.text!) \(LastnameTextfield.text!) and I attend \(SchoolTextfield.text!). I am currently in my \(year!) year and I own \(NumberofPets.text!) dogs. It is \(Morepetsswitch.isOn) that I want more pets."
               
               print(introduction)
        
        let alertController = UIAlertController(title: "My Introduction", message: introduction, preferredStyle: .alert)
                
                // A way to dismiss the box once it pops up
                let action = UIAlertAction(title: "Nice to meet you!", style: .default, handler: nil)
                
                // Passing this action to the alert controller so it can be dismissed
                alertController.addAction(action)
                
                present(alertController, animated: true, completion: nil)
            }
    @IBAction func Petstepper(_ sender: UIStepper) {
        NumberofPets.text = "\(Int(sender.value))"
    }
    
    override func viewDidLoad() {
        super.viewDidLoad()
        // Do any additional setup after loading the view.
    }


}
