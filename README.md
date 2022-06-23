- 👋 Hi, I’m @Control-Flow-Puppets
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
Control-Flow-Puppets/Control-Flow-Puppets is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
package com.perficient.testCases.us.ford.mobile;

import org.testng.annotations.Test;

import com.perficient.baseclasses.us.BSRPageElements_Mobile;
import com.perficient.baseclasses.us.CommonMethods;
import com.perficient.util.vehicle;
import com.prft.util.TestCaseBase;

public class BSRUS_VehicleBrochuresPage extends TestCaseBase {
	
	@Test(priority=1, groups= {"regression"}, description = "Ford US - Mobile - Brochures Page Verification", 
			testName = "Ford US - Mobile - Brochures Pages Verification")
	public void verifyBrochuresPageNavigation_FordUS() throws Exception{
		BSRPageElements_Mobile bsrBrochures = new BSRPageElements_Mobile(pageManager, excelReader, customAssertion);
		CommonMethods common = new CommonMethods(pageManager, excelReader, customAssertion);
		
			for(vehicle nameplate : common.loadTestNameplate().getTestFordNameplate()) {
				/**Open Vehicle brochures page*/
				bsrBrochures.goToFordNameplatePage(nameplate, "brochures",environment);
	            customAssertion.assertTrue(pageManager.getDriver().getCurrentUrl().contains("/brochures/"));
	            
		}
			
	}
			
			
	@Test(priority=2, groups= {"regression"}, description = "Ford US - Mobile - Brochures Page Verification", 
					testName = "Ford US - Mobile - Brochures Pages Verification")
	public void verifyVehicleBrochuresPage_FordUS() throws Exception{
				BSRPageElements_Mobile bsrBrochures = new BSRPageElements_Mobile(pageManager, excelReader, customAssertion);
				
	            if (bsrBrochures.isPageTitlePresent("Brochures"))
	            {
	            	pageManager.testpass("***Brochures Page verification***");
	            	
	            	pageManager.testpass(pageManager.getTitle());
       	         	pageManager.testpass(pageManager.getDriver().getCurrentUrl());
       	         
	            	/**verify Vehicle Brochures page*/
	            	bsrBrochures.verifyBrochuresGuides();
	            }
	            else {
	            	pageManager.testpass("Brochures page skipped.");
	            }
	            
			}
	}

